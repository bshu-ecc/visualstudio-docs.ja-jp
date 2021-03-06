---
title: "クイック アクション | Microsoft Docs"
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- CSharp
- VB
ms.openlocfilehash: 4ae2344bb1bce77d7e71cadf34660db57380f6b4
ms.sourcegitcommit: eb954434c34b4df6fd2264266381b23ce9e6204a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2017
---
# <a name="quick-actions"></a>クイック アクション

[クイック アクション](refactoring-code-generation-quick-actions.md#quick-actions)を使うと、コードのリファクタリング、生成、その他の変更を、1 つの操作で簡単に行うことができます。 クイック アクションは、C#、[C++](/cpp/ide/writing-and-refactoring-code-cpp)および Visual Basic のコード ファイルで使用できます。 クイック アクションには、言語に固有のものと、すべての言語が対象になるものがあります。 クイック アクションは、電球アイコン ![小さい電球アイコン](media/vs2015_lightbulbsmall.png "VS2017_LightBulbSmall") を使うか、または適切なコード行にカーソルを置いて **Ctrl** + **.** キーを押すと 適用できます。

赤い波線が表示され、Visual Studio が問題の修正候補を提供できる場合に、電球アイコンが表示されます。 たとえば、赤い波線で示されるエラーがある場合、そのエラーの修正が可能な場合に電球マークが表示されます。 いずれの言語でも、サードパーティは、たとえば SDK の一部として、カスタマイズした診断や提案を表示できます。Visual Studio はそれらの規則に基づいて電球マークを表示します。

## <a name="to-see-a-light-bulb"></a>電球マークを表示するには

1. 多くの場合、電球マークはマウスをエラーの地点に移動すると自動的に表示されます。あるいは、カレットをエラーのある行に移動すると、エディターの左端に表示されます。 赤い波線が表示されている場合にマウス ポインターを重ねると電球マークを表示させることができます。 問題が発生した行のどこかに、マウスやキーボードを使用して移動することで電球マークを表示させることもできます。

1. 行の任意の場所で **Ctrl** + **.** キーを押すと、 電球マークの表示を呼び出して修正候補のリストを直接表示できます。

   ![電球でのマウス ホバー](../ide/media/vs2015_lightbulb_hover.png "VS2017_LightBulb_Hover")

## <a name="to-see-potential-fixes"></a>修正候補を表示するには

下矢印をクリックするか、修正候補を表示するリンクをクリックすると、電球マークで実行可能なクイック操作のリストが表示されます。

![拡大電球](../ide/media/vs2015_lightbulb_hover_expanded.png "VS2017_LightBulb_hover_expanded")

## <a name="common-quick-actions"></a>共通のクイック アクション

ここでは、C# と Visual Basic 両方のコードに共通に適用されるクイック アクションを示します。

### <a name="add-missing-casesdefault-caseboth"></a>足りないケース、既定のケース、または両方を追加する

`switch` ステートメント (C#) または `Select Case` ステートメント (Visual Basic) を作成するときは、コード アクションを使って、足りないケース項目、既定のケースのステートメント、または両方を自動的に追加できます。  空のステートメントは次のようになります。

```csharp
enum MyEnum
{
    Item1,
    Item2,
    Item3
}

...

MyEnum myEnum = MyEnum.Item1;

switch(myEnum)
{
}
```

```vb
Enum MyEnum
    Item1
    Item2
    Item3
End Enum

...

Dim myEnum as MyEnum = MyEnum.Item1

Select Case myEnum
End Select
```

**[両方を追加する]** クイック アクションを使って足りないケースと既定のケースの両方を追加すると、次のようなコードが作成されます。

```csharp
switch(myEnum)
{
    case MyEnum.Item1:
        break;
    case MyEnum.Item2:
        break;
    case MyEnum.Item3:
        break;
    default:
        break;
}
```

```vb
Select Case myEnum
    Case MyEnum.Item1
        Exit Select
    Case MyEnum.Item2
        Exit Select
    Case Else
        Exit Select
End Select
```

### <a name="correct-misspelled-type"></a>スペルが正しくない型を修正する

Visual Studio で型のスペルを誤って入力した場合、このクイック アクションは自動的にそれを修正します。  電球メニューでは **['*スペルが正しくない型*' を '*スペルが正しい型*' に変更]** と表示されます。  例:

```csharp
// Before
private viod MyMethod()
{
}

// Change 'viod' to 'void'

// After
private void MyMethod()
{
}
```

```vb
' Before
Function MyFunction as Intger
End Function

' Change 'Intger' to 'Integer'

' After
Function MyFunction as Integer
End Function
```

### <a name="remove-unnecessary-cast"></a>不要なキャストを削除する

ある型をキャストが不要な別の型にキャストしている場合、**[不要なキャストの削除]** クイック アクション項目はキャストをコードから削除します。

```csharp
// before
int number = (int)3;

// Remove Unnecessary Cast

// after
int number = 3;
```

```vb
' Before
Dim number as Integer = CType(3, Integer)

' Remove Unnecessary Cast

' After
Dim number as Integer = 3
```

### <a name="replace-method-with-property-or-replace-property-with-method"></a>メソッドをプロパティに置き換える/プロパティをメソッドに置き換える

これらのクイック アクションは、メソッドをプロパティに、またはプロパティをメソッドに変換します。  次の例では、メソッドをプロパティに変更しています。  逆の場合は、単に *Before* セクションと *After* セクションが逆になります。

```csharp
private int MyValue;

// Before
public int GetMyValue()
{
    return MyValue;
}

// Replace 'GetMyValue' with property

// After
public int MyValue
{
    get { return MyValue; }
}
```

```vb
Dim MyValue As Integer

' Before
Function GetMyValue() As Integer
    Return MyValue
End Function

' Replace 'GetMyValue' with property

' After
ReadOnly Property MyValue As Integer
    Get
        Return MyValue
    End Get
End Property
```

### <a name="make-method-synchronous"></a>メソッドを同期させる

`async`/`Async` キーワードをメソッドで使う場合は、そのメソッド内のどこかで `await`/`Await` キーワードも使われることが予想されます。  ただし、そうではない場合は、クイック アクションが表示され、`async`/`Async` キーワードを削除して戻り値の型を変更することにより、同期メソッドにすることができます。  [クイック アクション] メニューの **[メソッドを同期させます]** オプションを選びます。

```csharp
// Before
async Task<int> MyAsyncMethod()
{
    return 3;
}

// Make method synchronous

// After
int MyAsyncMethod()
{
    return 3;
}
```

```vb
' Before
Async Function MyAsyncMethod() As Task(Of Integer)
    Return 3
End Function

' Make method synchronous

' After
Function MyAsyncMethod() As Integer
    Return 3
End Function
```

### <a name="make-method-asynchronous"></a>メソッドを非同期にする

メソッド内で `await`/`Await` キーワードを使うときは、メソッド自体に `async`/`Async` キーワードが指定されていることが想定されます。  ただし、そうではない場合は、クイック アクションが表示され、非同期メソッドにすることができます。  [クイック アクション] メニューの **[Make method/Function asynchronous (メソッド/関数を非同期にします)]** オプションを使います。

```csharp
// Before
int MyAsyncMethod()
{
    return await Task.Run(...);
}

// Make method synchronous

// After
async Task<int> MyAsyncMethod()
{
    return await Task.Run(...);
}
```

```vb
' Before
Function MyAsyncMethod() as Integer
    Return  Await Task.Run(...)
End Function

' Make method synchronous

' After
Async Function MyAsyncMethod() As Task(Of Integer)
    Return Await Task.Run(...)
End Function
```

### <a name="remove-unnecessary-usingsimports"></a>不必要な using/Import を削除する

**[不要な using の削除] / [不要なインポートの削除]** クイック アクションは、現在のファイルで使われていない `using` および `Import` ステートメントを削除します。  この項目を選ぶと、使われていない名前空間のインポートがすぐに削除されます。

### <a name="add-usingsimports-for-types-in-reference-assemblies-nuget-packages-or-other-types-in-your-solution"></a>参照アセンブリの型、NuGet パッケージの型、またはソリューション内の他の型に using/Import を追加する

ソリューション内の他のプロジェクトにある型を使うとクイック アクションが自動的に表示されますが、それ以外の場合は **[ツール] > [オプション] > [C#]** または **[Basic] > [詳細設定]** タブで有効にする必要があります。

* 参照アセンブリの型に using/import を提案する
* NuGet パッケージの型に using/import を提案する

有効にした場合、現在はインポートされていなくても参照アセンブリまたは NuGet パッケージには存在する名前空間の型を使うと、using/import ステートメントが作成されます。

```csharp
// Before
Debug.WriteLine("Hello");

// using System.Diagnostics;

// After
using System.Diagnostics;

Debug.WriteLine("Hello");
```

```vb
' Before
Debug.WriteLine("Hello")

' Imports System.Diagnostics

// After
Imports System.Diagnostics

Debug.WriteLine("Hello")
```

### <a name="convert-to-interpolated-string"></a>挿入文字列に変換する

[挿入文字列](/dotnet/csharp/language-reference/keywords/interpolated-strings)は、埋め込み変数を含む文字列を表現する簡単な方法であり、**[String.Format](https://msdn.microsoft.com/library/system.string.format.aspx)** メソッドに似ています。  このクイック アクションは、文字列が連結されている場合、または **String.Format** が使われている場合を認識し、それを挿入文字列に変更します。

```csharp
// Before
int num = 3;
string s = string.Format("My string with {0} in the middle", num);

// Convert to interpolated string

// After
int num = 3;
string s = $"My string with {num} in the middle";
```

```vb
' Before
Dim num as Integer = 3
Dim s as String = String.Format("My string with {0} in the middle", num)

' Convert to interpolated string

' After
Dim num as Integer = 3
Dim s As String = $"My string with {num} in the middle"
```

### <a name="remove-merge-conflict-markers"></a>マージ競合マーカーを削除する

このクイック アクションを使用すると、"変更を取り入れる" ことで競合するコードおよびマーカーが削除され、マージ競合を解決することができます。 (Visual Studio 2017 (バージョン 15.3 - プレビュー) でのみ使用できます。)

![リファクタリング - マージ競合を解決する](../ide/media/vside-refactoring-merge-conflicts.png)

### <a name="add-null-checks-for-parameters"></a>パラメーターの null チェックを追加する

このクイック アクションでは、パラメーターが null であるかどうかを示すチェックをコードに追加できます。 (Visual Studio 2017 (バージョン 15.3 - プレビュー) でのみ使用できます。)

![リファクタリング - null チェックを追加する](../ide/media/vside-refactoring-nullcheck.png)

### <a name="constructor-generator-improvements"></a>コンストラクターのジェネレーターの機能強化

このクイック アクションにより、コンストラクターを作成するときに、生成するプロパティまたはフィールドを選択したり、空の本文からコンストラクターを生成したりできるようになります。 呼び出しサイトから既存のコンストラクターにパラメーターを追加する場合にも使用できます。 (Visual Studio 2017 (バージョン 15.3 - プレビュー) でのみ使用できます。)

![リファクタリング - コンストラクターを生成する](../ide/media/vside-refactoring-constructors.png)

### <a name="remove-unused-variables"></a>未使用の変数を削除する

このクイック アクションでは、宣言されているがコードで一度も使用されていない変数を削除することができます。 (Visual Studio 2017 (バージョン 15.3 - プレビュー) でのみ使用できます。)

![リファクタリング - 未使用の変数](../ide/media/vside-refactoring-unusedvars.png)

### <a name="generate-overrides"></a>オーバーライドを生成する

このクイック アクションでは、クラスまたは構造体で空白の行からオーバーライドを作成することができます。 **[Pick Members (メンバーの選択)]** ダイアログ ボックスで、オーバーライドするメンバーを選択できます。 (Visual Studio 2017 (バージョン 15.3 - プレビュー) でのみ使用できます。)

![リファクタリング - オーバーライド](../ide/media/vside-refactoring-overrides.png)

![リファクタリング - ダイアログ ボックスをオーバーライドする](../ide/media/vside-refactoring-overrides-dialog.png)

### <a name="change-base-for-numeric-literals"></a>数値リテラルの基本を変更する

このクイック アクションでは、数値リテラルの基本数値システムを別のものに変換できます。 たとえば、数値を 16 進数からバイナリ形式に変更できます。 (Visual Studio 2017 (バージョン 15.3 - プレビュー) でのみ使用できます。)

![リファクタリング - 基本を変更する](../ide/media/vside-refactoring-changebase1.png)

![リファクタリング - 基本を変更する](../ide/media/vside-refactoring-changebase2.png)

### <a name="insert-digit-separators-into-literals"></a>リテラルに桁区切り記号を挿入する

このクイック アクションでは、区切り文字をリテラル値に追加することができます。 (Visual Studio 2017 (バージョン 15.3 - プレビュー) でのみ使用できます。)

![リファクタリング - 桁区切り記号を変更する](../ide/media/vside-refactoring-separators.png)

### <a name="convert-if-construct-to-switch"></a>**if** コンストラクトを **switch** に変換する

このクイック アクションでは、**if-then-else** コンストラクトを **switch** コンストラクトに変換することができます。 (Visual Studio 2017 (バージョン 15.3 - プレビュー) でのみ使用できます。)

```csharp
// Before
if (obj is string s)
{
  Console.WriteLine("obj is a string: " + s);
}

else if (obj is int i && i > 10)
{
  Console.WriteLine("obj is an int greater than 10");
}

// Convert to switch

// After
switch (obj)
{
  case string s:
    Console.WriteLine("Obj is a string: " + s);
    break;
  case int i when i > 10:
    Console.WriteLine("obj is an int greater than 10");
    break;
}
```

```vb
' Before
If TypeOf obj Is String s Then
    Console.WriteLine("obj is a string: " + s)
Else If TypeOf obj Is Integer i And i > 10 Then
    Console.WriteLine("obj is an int greater than 10")
End If

' Convert to switch

' After
Select Case obj
  Case String s
    Console.WriteLine("Obj is a string: " + s)
    Exit Sub
  Case Integer i when i > 10
    Console.WriteLine("obj is an int greater than 10")
    Exit Sub
End Select
```

## <a name="see-also"></a>関連項目

[コード スタイルとクイック アクション](code-styles-and-quick-actions.md)  
[コードの作成とリファクタリング (C++)](/cpp/ide/writing-and-refactoring-code-cpp)
