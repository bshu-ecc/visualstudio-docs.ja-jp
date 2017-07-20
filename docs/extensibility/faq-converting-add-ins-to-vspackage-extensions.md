---
title: "FAQ: アドインを VSPackage 拡張機能に変換する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a01d333-6e31-423f-ae06-5091a4fcb7a9
caps.latest.revision: 22
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: dd7451b090cb9f25f85d08341b6d38130a13942b
ms.lasthandoff: 02/22/2017

---
# <a name="faq-converting-add-ins-to-vspackage-extensions"></a>FAQ: アドインを VSPackage 拡張に変換する
現在、アドインは推奨されていません。 新しい Visual Studio 拡張機能をするためには、VSIX 拡張機能を作成する必要があります。 ここでは、VSIX 拡張機能を Visual Studio アドインを変換する方法に関するいくつかのよく寄せられる質問に対する回答を示します。  
  
> [!WARNING]
>  C# および Visual Basic のプロジェクトの Visual Studio 2015 以降、VSIX プロジェクトを使用し、メニュー コマンド、ツール ウィンドウおよび VSPackages の項目テンプレートを追加できます。 詳細については、次を参照してください。 [what ' s New in Visual Studio 2015 SDK](../extensibility/what-s-new-in-the-visual-studio-2015-sdk.md)します。  
  
> [!IMPORTANT]
>  多くの場合、アドインのコードを VSPackage プロジェクト項目を含む VSIX プロジェクトに単に転送できます。 呼び出して、DTE オートメーション オブジェクトを取得する<xref:Microsoft.VisualStudio.Shell.Package.GetService%2A>で、<xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A>メソッド</xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A></xref:Microsoft.VisualStudio.Shell.Package.GetService%2A>。  
>   
>  `DTE2 dte = (DTE2)GetService(typeof(DTE));`  
>   
>  詳細については、次を参照してください。 [VSPackage でアドイン コードを実行できますか?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_RunAddin)以下です。  
  
## <a name="what-software-do-i-need-to-develop-vsix-extensions"></a>VSIX 拡張機能を開発する必要があるソフトウェアをでしょうか。  
 Visual Studio 2015 以降、インストールしない、Visual Studio SDK ダウンロード センターからです。 Visual Studio のセットアップのオプション機能として含まれます。 後で、VS SDK をインストールすることもできます。 詳細については、次を参照してください。 [Visual Studio SDK をインストールする](../extensibility/installing-the-visual-studio-sdk.md)です。  
  
## <a name="wheres-the-extension-documentation"></a>拡張機能のドキュメントはどこですか。  
 始まる[Visual Studio 拡張機能の開発を始めた](../extensibility/starting-to-develop-visual-studio-extensions.md)します。 MSDN の VSSDK 拡張機能の開発に関するその他の記事は、1 つ次に示します。  
  
## <a name="can-i-convert-my-add-in-project-to-a-vsix-project"></a>アドイン プロジェクトを VSIX プロジェクトは変換できますか。  
 アドイン プロジェクトは、VSIX プロジェクトで使用される機構は、アドイン プロジェクトにあるものと同じではありませんので、VSIX プロジェクトに直接変換できません。 VSIX プロジェクトのテンプレートと適切なプロジェクト項目テンプレートを使用する比較的簡単に開始して VSIX 拡張機能として実行されているコードの多くがあります。  
  
##  <a name="a-namebkmkstartdevelopinga-how-do-i-start-developing-vsix-extensions"></a><a name="BKMK_StartDeveloping"></a>VSIX 拡張機能の開発を開始する方法  
 メニュー コマンドが使用できる VSIX を作成する方法を次に示します。  
  
#### <a name="to-make-a-vsix-extension-that-has-a-menu-command"></a>VSIX の拡張機能メニュー コマンドが使用できるようにするには  
  
1.  VSIX プロジェクトを作成する。 (**ファイル**、**新規**、**プロジェクト**、または型**プロジェクト**で、**クイック起動**ウィンドウ)。 **新しいプロジェクト** ダイアログ ボックスで、展開**Visual c#/機能拡張**または**Visual Basic/機能拡張**を選択し、 **VSIX プロジェクト**)。プロジェクトに名前を**TestExtension**し、場所を指定します。  
  
2.  追加、**にカスタム コマンド**プロジェクト項目テンプレートです。 (でプロジェクト ノードを右クリックし、**ソリューション エクスプ ローラー**選択**追加/新しい項目の**です。 **新しいプロジェクト**Visual c# または Visual Basic では、選択のダイアログ ボックス、**拡張**ノード**にカスタム コマンド**)。  
  
3.  F5 キーを押して、プロジェクトをデバッグ モードでビルドおよび実行します。  
  
     Visual Studio の&2; 番目のインスタンスが表示されます。 この&2; 番目のインスタンスは実験用インスタンスと呼ばれます。コードの記述に使用する Visual Studio のインスタンスとは設定が異なることがあります。 実験用インスタンスを初めて実行するときには、VS Online にサインインしてテーマとプロファイルを指定するよう求められます。  
  
     **ツール** メニュー (に実験用インスタンス) という名前のボタンを表示する必要があります**マイ コマンド名**します。 このボタンを選択すると、メッセージが表示される必要があります:**内 TestVSPackagePackage.MenuItemCallback()**します。  
  
##  <a name="a-namebkmkrunaddina-how-can-i-run-my-add-in-code-in-a-vspackage"></a><a name="BKMK_RunAddin"></a>VSPackage でアドイン コードを実行する方法はありますか  
 通常、アドイン コードは次の&2; つの方法のどちらかで実行します。  
  
-   メニュー コマンドによるトリガー (コードは `IDTCommandTarget.Exec` メソッド内にあります)  
  
-   起動時に自動的に実行 (コードは `OnConnection` イベント ハンドラー内にあります)。  
  
 VSPackage でも同じ操作を実行できます。 コールバック メソッドにアドイン コードを追加する方法を次に示します。  
  
#### <a name="to-implement-a-menu-command-in-a-vspackage"></a>VSPackage にメニュー コマンドを実装するには  
  
1.  メニュー コマンドを含む VSPackage を作成します。 (詳細については、次を参照してください[メニュー コマンドを使用して拡張機能の作成](../extensibility/creating-an-extension-with-a-menu-command.md)。)。  
  
2.  VSPackage の定義が含まれているファイルを開きます。 (C# プロジェクトである*\<プロジェクト名 >*Package.cs です)。  
  
3.  ファイルに次の `using` ステートメントを追加します。  
  
    ```c#  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
4.  
          `MenuItemCallback` メソッドを見つけます。 呼び出しを追加して<xref:Microsoft.VisualStudio.Shell.Package.GetService%2A>を取得する、<xref:EnvDTE80.DTE2>オブジェクト:</xref:EnvDTE80.DTE2> </xref:Microsoft.VisualStudio.Shell.Package.GetService%2A>  
  
    ```c#  
    DTE2 dte = (DTE2)GetService(typeof(DTE));  
    ```  
  
5.  アドインのコードを `IDTCommandTarget.Exec` メソッドに追加します。 たとえば、新しいウィンドウを追加するいくつかのコードをここでは、**出力**ウィンドウとペインに"Some Text"を出力します。  
  
    ```c#  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        DTE2 dte = (DTE2) GetService(typeof(DTE));  
        OutputWindow outputWindow = dte.ToolWindows.OutputWindow;  
  
        OutputWindowPane outputWindowPane = outputWindow.OutputWindowPanes.Add("A New Pane");  
        outputWindowPane.OutputString("Some Text");  
    }  
  
    ```  
  
6.  このプロジェクトをビルドして実行します。 F5 キーを押すか、選択**開始**上、**デバッグ**ツールバーです。 Visual Studio の実験用インスタンスで、**ツール**という名前のボタンがメニューにあります**マイ コマンド名**します。 このボタンは、単語を選択すると**Some Text**に表示する必要があります、**出力**ウィンドウ ペイン。 (を開く必要があります、**出力**ウィンドウです)。  
  
 起動時にコードを実行することもできます。 ただし、VSPackage 拡張機能では通常、この方法はお勧めできません。 Visual Studio の起動時に読み込まれる拡張機能が多すぎると、起動にかかる時間がかなり長くなることがあります。 何らかの条件 (ソリューションが開いているなど) に一致した場合にのみ VSPackage を自動的に読み込むようにしておくことをお勧めします。  
  
 この手順では、ソリューションが開いているときに自動的に読み込まれる VSPackage のアドイン コードを実行する方法を示します。  
  
#### <a name="to-autoload-a-vspackage"></a>VSPackage を自動読み込みさせるには  
  
1.  Visual Studio パッケージ プロジェクト項目には、VSIX プロジェクトを作成します。 (これを行う手順については、次を参照してください。 [VSIX 拡張機能の開発を開始する方法ですか?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_StartDeveloping)します。 追加するだけで、 **Visual Studio パッケージ**代わりにプロジェクト項目です)。VSIX プロジェクトに名前を**TestAutoload**します。  
  
2.  TestAutoloadPackage.cs を開きます。 パッケージ クラスが宣言されている行を見つけます。  
  
    ```c#  
    public sealed class <name of your package>Package : Package  
    ```  
  
3.  この行の上に、一連の属性が記述されています。 次の属性を追加します。  
  
    ```c#  
    [ProvideAutoLoad(UIContextGuids80.SolutionExists)]  
    ```  
  
4.  
          `Initialize()` メソッド内にブレークポイントを設定し、デバッグを開始します (F5)。  
  
5.  この実験用インスタンスで、プロジェクトを開きます。 VSPackage が読み込まれ、ブレークポイントにヒットします。  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80>。</xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80>のフィールドを使用して、VSPackage を読み込むには、他のコンテキストを指定することができます。 詳細については、次を参照してください。[読み込み VSPackages](../extensibility/loading-vspackages.md)します。  
  
## <a name="how-can-i-get-the-dte-object"></a>DTE オブジェクトは入手するにはどうしたらよいですか?  
 アドインが UI (メニュー コマンド、ツールバー ボタン、ツール ウィンドウなど) を表示しない場合、VSPackage から DTE オートメーション オブジェクトを入手できる限り、コードを変更せずにそのまま使用できます。 次の手順に従います。  
  
#### <a name="to-get-the-dte-object-from-a-vspackage"></a>VSPackage から DTE オブジェクトを取得するには  
  
1.  VSIX プロジェクトと Visual Studio パッケージ項目テンプレートには、検索、 *\<プロジェクト名 >*Package.cs ファイルです。 これは、クラスから派生した<xref:Microsoft.VisualStudio.Shell.Package>; Visual Studio を操作することはできます</xref:Microsoft.VisualStudio.Shell.Package>。 この場合は、使用する、<xref:Microsoft.VisualStudio.Shell.Package.GetService%2A>を取得する、<xref:EnvDTE80.DTE2>オブジェクト</xref:EnvDTE80.DTE2></xref:Microsoft.VisualStudio.Shell.Package.GetService%2A>。  
  
2.  次の `using` ステートメントを追加します。  
  
    ```c#  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
3.  
          `Initialize` メソッドを見つけます。 このメソッドは、パッケージ ウィザードで指定したコマンドを処理します。 呼び出しを追加して<xref:Microsoft.VisualStudio.Shell.Package.GetService%2A>DTE オブジェクトを取得する:</xref:Microsoft.VisualStudio.Shell.Package.GetService%2A>  
  
    ```c#  
    DTE dte = (DTE)GetService(typeof(DTE));  
    ```  
  
 作成したら、<xref:EnvDTE.DTE>オートメーション オブジェクトをプロジェクトに、アドインのコードの残りの部分を追加することができます</xref:EnvDTE.DTE>。 必要がある場合、<xref:EnvDTE80.DTE2>オブジェクト、同じ処理を行うことができます</xref:EnvDTE80.DTE2>。  
  
## <a name="how-do-i-change-menu-commands-and-toolbar-buttons-in-my-add-in-to-the-vspackage-style"></a>アドインのメニュー コマンドとツールバー ボタンを VSPackage スタイルで変更するにはどうしたらよいですか?  
 VSPackage 拡張機能は、ほとんどのメニュー コマンド、ツールバー、ツールバー ボタン、その他の UI を作成するときに .vsct ファイルを使用します。 **にカスタム コマンド**プロジェクト項目テンプレートを使用して、オプションのコマンドを作成する、**ツール**メニュー。 詳細については、次を参照してください。[メニュー コマンドを使用して拡張機能の作成](../extensibility/creating-an-extension-with-a-menu-command.md)します。  
  
 .Vsct ファイルの詳細については、次を参照してください。[方法 vspackages にある追加のユーザー インターフェイス要素](../extensibility/internals/how-vspackages-add-user-interface-elements.md)します。 .Vsct ファイルを使用してメニュー項目、ツールバー、およびツール バー ボタンを追加する方法について説明するチュートリアルでは、次を参照してください。[拡張メニューとコマンド](../extensibility/extending-menus-and-commands.md)します。  
  
## <a name="how-do-i-add-custom-tool-windows-in-the-vspackage-way"></a>VSPackage を使用してカスタム ツールウィンドウを追加するにはどうしたらよいですか?  
 カスタム ツール ウィンドウのプロジェクト項目テンプレートを使用すると、ツール ウィンドウを作成できます。 このプロジェクト項目テンプレートに関する詳細については、次を参照してください。[ツール ウィンドウで、拡張機能を作成する](../extensibility/creating-an-extension-with-a-tool-window.md)です。 ツール ウィンドウについては、次を参照してください。[の拡張とカスタマイズ ツール ウィンドウ](../extensibility/extending-and-customizing-tool-windows.md)および、その下にある記事は、特に[ツール ウィンドウを追加する](../extensibility/adding-a-tool-window.md)です。  
  
## <a name="how-do-i-manage-visual-studio-windows-in-the-vspackage-way"></a>VSPackage を使用して Visual Studio ウィンドウを管理するにはどうしたらよいですか?  
 Visual Studio ウィンドウを管理するアドインの場合、そのアドイン コードは VSPackage で機能します。 この手順が管理するコードを追加する方法を示しますなど、**タスク一覧**に、 `MenuItemCallback` VSPackage のメソッドです。  
  
#### <a name="to-insert-window-management-code-from-an-add-in-into-a-vspackage"></a>アドインのウィンドウ管理コードを VSPackage に挿入するには  
  
1.  メニュー コマンドのある VSPackage を作成、 [VSIX 拡張機能の開発を開始する方法ですか?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_StartDeveloping)セクションです。  
  
2.  VSPackage の定義が含まれているファイルを開きます。 (C# プロジェクトである*\<プロジェクト名 >*Package.cs です)。  
  
3.  次の `using` ステートメントを追加します。  
  
    ```c#  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
4.  
          `MenuItemCallback` メソッドを見つけます。 呼び出しを追加して<xref:Microsoft.VisualStudio.Shell.Package.GetService%2A>を取得する、<xref:EnvDTE80.DTE2>オブジェクト:</xref:EnvDTE80.DTE2> </xref:Microsoft.VisualStudio.Shell.Package.GetService%2A>  
  
    ```c#  
    DTE2 dte = (DTE2)GetService(typeof(DTE));  
    ```  
  
5.  アドインのコードを追加します。 たとえば、新しいタスクを追加するコードをここでは、**タスク一覧**のタスクの数を示し、1 つのタスクを削除します。  
  
    ```c#  
    private void MenuItemCallback(object sender, EventArgs e)   
    {  
        DTE2 dte = (DTE2) GetService(typeof(DTE));   
  
        TaskList tl = (TaskList)dte.ToolWindows.TaskList;   
        askItem tlItem;   
  
        // Add a couple of tasks to the Task List.   
        tlItem = tl.TaskItems.Add(" ", " ", "Test task 1.",    
            vsTaskPriority.vsTaskPriorityHigh, vsTaskIcon.vsTaskIconUser,   
            true, "", 10, true, true);  
        tlItem = tl.TaskItems.Add(" ", " ", "Test task 2.",   
            vsTaskPriority.vsTaskPriorityLow, vsTaskIcon.vsTaskIconComment, true, "", 20, true,true);  
  
        // List the total number of task list items after adding the new task items.  
        System.Windows.Forms.MessageBox.Show("Task Item 1 description: "+tl.TaskItems.Item(2).Description);  
        System.Windows.Forms.MessageBox.Show("Total number of task items: "+tl.TaskItems.Count);   
  
        // Remove the second task item. The items list in reverse numeric order.   
        System.Windows.Forms.MessageBox.Show("Deleting the second task item");  
        tl.TaskItems.Item(2).Delete();  
        System.Windows.Forms.MessageBox.Show("Total number of task items: "+tl.TaskItems.Count);   
    }  
    ```  
  
## <a name="how-do-i-manage-projects-and-solutions-in-a-vspackage"></a>VSPackage でプロジェクトとソリューションを管理するにはどうしたらよいですか?  
 プロジェクトとソリューションを管理するアドインの場合、そのアドイン コードは VSPackage で機能します。 たとえば、スタートアップ プロジェクトを取得するコードを追加する手順を次に示します。  
  
1.  メニュー コマンドのある VSPackage を作成、 [VSIX 拡張機能の開発を開始する方法ですか?](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md#BKMK_StartDeveloping)セクションです。  
  
2.  VSPackage の定義が含まれているファイルを開きます。 (C# プロジェクトである*\<プロジェクト名 >*Package.cs です)。  
  
3.  次の `using` ステートメントを追加します。  
  
    ```c#  
    using EnvDTE;  
    using EnvDTE80;  
    ```  
  
4.  
          `MenuItemCallback` メソッドを見つけます。 呼び出しを追加して<xref:Microsoft.VisualStudio.Shell.Package.GetService%2A>を取得する、<xref:EnvDTE80.DTE2>オブジェクト:</xref:EnvDTE80.DTE2> </xref:Microsoft.VisualStudio.Shell.Package.GetService%2A>  
  
    ```c#  
    DTE2 dte = (DTE2)GetService(typeof(DTE));  
    ```  
  
5.  アドインのコードを追加します。 たとえば、次のコードはソリューション内のスタートアップ プロジェクトの名前を取得します。 (このパッケージを実行するときには、マルチプロジェクト ソリューションが開いている必要があります。)  
  
    ```c#  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        DTE2 dte = (DTE2) GetService(typeof(DTE));   
  
        SolutionBuild2 sb = (SolutionBuild2)dte.Solution.SolutionBuild;   
        Project startupProj;   
        string msg = "";  
  
        foreach (String item in (Array)sb.StartupProjects)   
        {  
            msg += item;   
        }  
        System.Windows.Forms.MessageBox.Show("Solution startup Project: "+msg);   
        startupProj = dte.Solution.Item(msg);   
        System.Windows.Forms.MessageBox.Show("Full name of solution's startup project: "+"/n"+startupProj.FullName);   
    }  
    ```  
  
## <a name="how-do-i-set-keyboard-shortcuts-in-a-vspackage"></a>VSPackage でキーボード ショートカットを設定するにはどうしたらよいですか?  
 .vsct ファイルの `<KeyBindings>` 要素を使用します。 次の例では、`idCommand1` コマンドのキーボード ショートカットは Alt+A、`idCommand2` コマンドのキーボード ショートカットは Alt+Ctrl+A です。 キー名の構文に注意してください。  
  
```xml  
<KeyBindings>  
    <KeyBinding guid="MyProjectCmdSet" id="idCommand1" editor="guidVSStd97" key1="A" mod1="ALT" />  
    <KeyBinding guid="MyProjectCmdSet" id="idCommand2" editor="guidVSStd97" key1="A" mod1="CONTROL" mod2="ALT" />  
</KeyBindings>  
```  
  
## <a name="how-do-i-handle-automation-events-in-a-vspackage"></a>VSPackage でオートメーション イベントを処理するにはどうしたらよいですか?  
 VSPackage では、アドインと同様の方法でオートメーション イベントを処理します。 
          `OnItemRenamed` イベントを処理する方法を次のコードに示します。 (この例は、DTE オブジェクトを既に取得していることを前提としています。)  
  
```c#  
Events2 dteEvents = (Events2)dte.Events;  
dteEvents.ProjectItemsEvents.ItemRenamed += listener1.OnItemRenamed;   
. . .  
public void OnItemRenamed(EnvDTE.ProjectItem projItem, string oldName)   
{  
    string s = "[Event] Renamed " + oldName + " to " + Path.GetFileName(projItem.get_FileNames(1) + " in project " + projItem.ContainingProject.Name;   
}  
```