---
title: "チュートリアル: ClickOnce 配置 API で必要に応じてサテライト アセンブリをダウンロードする |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, globalization
- localization, Windows Forms
- Windows Forms, localization
- globalization, ClickOnce
- satellite assemblies, ClickOnce
- ClickOnce deployment, on-demand download
- localization, ClickOnce deployment
- ClickOnce deployment, localization
ms.assetid: fdaa553f-a27e-44eb-a4e2-08c122105a87
caps.latest.revision: "11"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: c3c3b817975304a41181b5e346a32b0b95c4258e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api"></a>チュートリアル : ClickOnce 配置 API を使用して必要に応じてサテライト アセンブリをダウンロードする
サテライト アセンブリを使用すると、複数のカルチャに対して Windows フォーム アプリケーションを構成できます。 *サテライト アセンブリ* とは、アプリケーションの既定のカルチャ以外のカルチャ用アプリケーション リソースを含むアセンブリのことです。  
  
 説明したよう[ClickOnce アプリケーションのローカライズ](../deployment/localizing-clickonce-applications.md)、同じ内に複数のカルチャ用の複数のサテライト アセンブリを含めることができます[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]展開します。 既定では、 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] により配置に含まれるすべてのサテライト アセンブリがクライアント コンピューターにダウンロードされます。ただし、多くの場合、1 つのクライアントに必要なサテライト アセンブリは 1 つだけです。  
  
 このチュートリアルでは、サテライト アセンブリをオプションとしてマークする方法、および現在のカルチャ設定にクライアント コンピューターが必要とするアセンブリのみをダウンロードする方法について説明します。 次の手順では、 [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]から入手できるツールを使用します。 このタスクを、 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]を使用して実行することもできます。  「 [チュートリアル: デザイナーを使用し、ClickOnce 配置 API で必要に応じてサテライト アセンブリをダウンロードする](http://msdn.microsoft.com/library/ms366788\(v=vs.110\)) 」または「 [チュートリアル: デザイナーを使用し、ClickOnce 配置 API で必要に応じてサテライト アセンブリをダウンロードする](http://msdn.microsoft.com/library/ms366788\(v=vs.120\))」もご覧ください。  
  
> [!NOTE]
>  次のコード例は、テストを目的としているため、プログラム内でカルチャを `ja-JP`に設定しています。 このコードを運用環境用に調整する方法については、このトピックの「次の手順」セクションを参照してください。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このトピックでは、ローカライズされたリソースを、Visual Studio を使用してアプリケーションに追加する方法を理解していることを想定しています。 手順について詳しくは、「 [チュートリアル: Windows フォームのローカリゼーション](https://msdn.microsoft.com/en-us/library/vstudio/y99d1cd3\(v=vs.100\).aspx)」をご覧ください。  
  
### <a name="to-download-satellite-assemblies-on-demand"></a>必要に応じてサテライト アセンブリをダウンロードするには  
  
1.  アプリケーションに次のコードを追加して、サテライト アセンブリのオンデマンドでのダウンロードを有効にします。  
  
     [!code-csharp[ClickOnce.SatelliteAssembliesSDK#1](../deployment/codesnippet/CSharp/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api_1.cs)]
     [!code-vb[ClickOnce.SatelliteAssembliesSDK#1](../deployment/codesnippet/VisualBasic/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api_1.vb)]  
  
2.  使用して、アプリケーションのサテライト アセンブリを生成[Resgen.exe (リソース ファイル ジェネレーター)](/dotnet/framework/tools/resgen-exe-resource-file-generator)または[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]です。  
  
3.  MageUI.exe を使用して、アプリケーション マニフェストを生成するか、または既存のアプリケーション マニフェストを開きます。 このツールの詳細については、次を参照してください。 [MageUI.exe (マニフェスト生成および編集ツールのグラフィカル クライアント)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)です。  
  
4.  **[Files]** タブをクリックします。  
  
5.  **省略記号** (**...**) ボタンをクリックして、アプリケーションのすべてのアセンブリとファイル (Resgen.exe を使用して生成したサテライト アセンブリを含む) を格納しているディレクトリを選択します (サテライト アセンブリの名前は、" *isoCode*\ApplicationName.resources.dll" という形式で付けられます。 *isoCode* は RFC 1766 形式の言語識別子を表します)。  
  
6.  **[作成]** をクリックして、配置にファイルを追加します。  
  
7.  各サテライト アセンブリの **[省略可能]** チェック ボックスをオンにします。  
  
8.  各サテライト アセンブリの [グループ] フィールドに ISO 言語識別子を設定します。 たとえば、日本語のサテライト アセンブリであれば、ダウンロード グループ名として「 `ja-JP`から入手できるツールを使用します。 これにより、ユーザーの <xref:System.Threading.Thread.CurrentUICulture%2A> プロパティの設定に応じて該当するサテライト アセンブリをダウンロードする、手順 1 で追加したコードが有効になります。  
  
## <a name="next-steps"></a>次の手順  
 コード例を見ると、 <xref:System.Threading.Thread.CurrentUICulture%2A> が特定の値に設定されています。しかし、運用環境では、クライアント コンピューターに適切な値が既定で設定されるため、この行は削除する必要があります。 たとえば、アプリケーションを日本語のクライアント コンピューターで実行する場合、既定では <xref:System.Threading.Thread.CurrentUICulture%2A> が `ja-JP` になります。 ここでは、アプリケーションの配置前にサテライト アセンブリをテストするという趣旨でプログラムから値を設定しています。  
  
## <a name="see-also"></a>関連項目  
 [ClickOnce アプリケーションのローカライズ](../deployment/localizing-clickonce-applications.md)