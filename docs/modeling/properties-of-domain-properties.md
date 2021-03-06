---
title: "ドメインのプロパティを |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, domain properties
ms.assetid: a9471562-d6f2-46bf-9872-e0d66ba03150
caps.latest.revision: "24"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 58402e1030516e6f587ec428bd98179ff82ec43a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="properties-of-domain-properties"></a>ドメイン プロパティのプロパティ
A*ドメイン プロパティ*値を保持できるモデル要素の機能です。 たとえば、`Person` ドメイン クラスに `Name` プロパティと `BirthDate` プロパティを指定することができます。 DSL 定義で、ドメイン プロパティは図のドメイン クラス ボックスと DSL エクスプローラーのドメイン クラスの下に一覧表示されます。 詳細については、次を参照してください。[ドメイン固有言語の定義方法](../modeling/how-to-define-a-domain-specific-language.md)です。  
  
> [!NOTE]
>  "プロパティ" という用語には 2 つの使用法があります。 A*ドメイン プロパティ*ドメイン クラスで定義する機能です。 これに対し、DSL のさまざまな要素が*プロパティ*に記載されている、**プロパティ**DSL 定義のウィンドウ。 たとえば、すべてのドメイン プロパティは、このトピックで説明するプロパティのセットを持っています。  
  
 実行時、ユーザーがドメイン クラスのインスタンスを作成すると、ドメイン プロパティの値は [プロパティ] ウィンドウ内と図形上に表示されます。  
  
 ほとんどのドメイン プロパティは通常の CLR プロパティとして実装されます。 ただし、プログラミングの観点から、ドメイン プロパティには以下のように、通常プログラム プロパティより豊富な機能が含まれています。  
  
-   プロパティの状態を監視する規則とイベントを定義できます。 詳細については、次を参照してください。[への応答と変更を反映する](../modeling/responding-to-and-propagating-changes.md)です。  
  
-   トランザクションは一貫性のない状態を防ぐのに役立ちます。 詳細については、次を参照してください。[を移動すると、プログラム コードでモデルを更新する](../modeling/navigating-and-updating-a-model-in-program-code.md)です。  
  
 図中または DSL エクスプローラー内のドメイン プロパティを選択すると、[プロパティ] ウィンドウに以下の項目が表示されます。 これらの項目を使用する方法の詳細については、次を参照してください。[をカスタマイズすると、ドメイン固有言語の拡張](../modeling/customizing-and-extending-a-domain-specific-language.md)です。  
  
|プロパティ|説明|既定値|  
|--------------|-----------------|-------------------|  
|**説明**|生成されたデザイナーのユーザー インターフェイス (UI) についてのドキュメントとして使用される説明。|\<なし >|  
|**表示名**|生成されたデザイナーで、このドメイン プロパティ向けに表示される名前。 空白および句読点を含むことがあります。たとえば、"Song Title" など。|\<なし >|  
|**要素名プロバイダー**|これは `Is Element Name` を `true` に設定した場合のみ適用されます。 ドメイン クラスの新しい要素の名前を指定するコードを作成し、既定の動作をオーバーライドすることができます。<br /><br /> DSL プロジェクト内のコード ファイルで、<xref:Microsoft.VisualStudio.Modeling.ElementNameProvider> から派生するクラスを作成します。<br /><br /> 次に、DSL エクスプローラーで、DSL のルートを右クリックし、[外部型の追加] をクリックします。 クラスの名前を入力します。<br /><br /> 再度このドメイン プロパティを選択し、ドロップダウン リストからクラスの名前を選択します。|\<なし >|  
|**Get アクセス操作子のアクセス修飾子**|ドメイン クラスのアクセスのレベル (`public` または `internal`)。 これはプログラム コードがプロパティをアクセスできる範囲を制御します。|`public`|  
|**ヘルプ キーワード**|このドメイン プロパティに対して、F1 ヘルプのインデックスを作成するために使用される、オプションのキーワード。|\<なし >|  
|**参照可能**|`True` の場合、ドメイン プロパティは、DSL のモデルが開いているときに、プロパティ ウィンドウに表示されます。<br /><br /> `False` の場合、ドメイン プロパティは UI で非表示になります。<br /><br /> 表示されますが、読み取り専用ドメインのプロパティを作成する場合は、設定**は UI 読み取り専用**です。|`True`|  
|**要素名は、します。**|`True` の場合、このドメイン プロパティは、DSL エクスプローラーで、モデル要素の名前として表示されます。<br /><br /> 新しいモデル要素はこのプロパティに対して一意の既定値を受け取ります。 これらの値を生成する方法を制御する場合は、設定**要素名プロバイダー**です。|`False`|  
|**UI は読み取り専用**|`True` の場合、ドメイン プロパティの値は UI を使用して変更できません。 ただし、プログラムにより設定可能で、[プロパティ] ウィンドウに表示されます。<br /><br /> ユーザーからドメインのプロパティを非表示にする場合は、設定**は参照可能な**します。 プログラムでアクセスを制御する場合は、設定**セッターのアクセス修飾子**です。|`False`|  
|**種類**|ドメイン プロパティの種類 (`Normal`、`Calculated`、または `CustomStorage`)。 詳細については、次を参照してください。[記憶域のカスタム プロパティして計算された](../modeling/calculated-and-custom-storage-properties.md)です。|`Normal`|  
|**名前**|このドメイン プロパティの名前。 これは、必要があります、有効な識別子では、たとえば**SongTitle**です。|\<なし >|  
|**注**|このドメイン プロパティに関連付けられる非公式な注釈。|\<なし >|  
|**Set アクセス操作子のアクセス修飾子**|Setter 用のアクセス修飾子。 これはプログラム コードがプロパティを設定できる範囲を制御します。|`public`|  
|**Type**|プロパティの種類。 利用可能な種類の一覧に追加、DSL のエクスプ ローラーでの DSL のルートを右クリックし、クリックして**外部型の追加**です。|`String`|  
  
## <a name="see-also"></a>関連項目  
 [ドメイン固有言語ツールの用語集](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)