---
title: "Office ソリューションの配置 |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ClickOnce deployment [Office development in Visual Studio], event viewer
- deploying applications [Office development in Visual Studio], event viewer
- Office applications [Office development in Visual Studio], deploying Office solutions
- Office development in Visual Studio, deploying Office solutions
- ClickOnce deployment [Office development in Visual Studio], troubleshooting
- deploying applications [Office development in Visual Studio], Office solutions (2007 system)
- Office development in Visual Studio, troubleshooting
- Office development in Visual Studio, event viewer
- ClickOnce deployment [Office development in Visual Studio], about ClickOnce solution deployments
- Office solutions [Office development in Visual Studio], deploying
- deploying applications [Office development in Visual Studio], troubleshooting
- solutions [Office development in Visual Studio], deploying Office solutions (2007 system)
ms.assetid: 4cdf4bc6-72c5-4166-8019-d5fd61281079
caps.latest.revision: "78"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5e9511e8fca3e1a6b02b764f21acf71c6535fc05
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="deploying-an-office-solution"></a>Office ソリューションの配置
  ClickOnce または Windows インストーラーを使用して、Office ソリューションを配置できます。 ClickOnce を使用すると、ソリューションを配置および更新するために必要な手順の数を減らすことができます。 Windows インストーラーを使用する場合は、ユーザーがソリューションをインストールする際に、ソリューションをどのようにインストールするか、およびセットアップ プログラムがどのページを表示するかを制御できます。  
  
> [!NOTE]  
>  間での Office エクスペリエンスを拡張するソリューションの開発に関心のある[複数のプラットフォーム](https://dev.office.com/add-in-availability)しますか? チェック アウト新しい[Office アドイン モデル](https://dev.office.com/docs/add-ins/overview/office-add-ins)です。 Office アドインは VSTO アドインやソリューションと比較して、小さなフット プリントを持ち、ほぼすべての web プログラミング HTML5、JavaScript、CSS3、XML などのテクノロジを使用してそれらをビルドすることができます。  
  
## <a name="deploying-a-solution-by-using-clickonce"></a>ClickOnce を使用したソリューションの配置  
 ClickOnce を使用してソリューションを配置するときは、ユーザーがインストールして実行できる中央の場所にソリューションを発行します。 新しいセットアップ プログラムをユーザーに配布しなくても、ソリューションを更新できます。  この配置オプションの方が簡単ですが、ユーザーにカスタム設定ページを表示できません。 また、複数のユーザーがいるコンピューターでは、ソリューションを複数回インストールする必要があります。 参照してください[ClickOnce を使用して Office ソリューションの配置](../vsto/deploying-an-office-solution-by-using-clickonce.md)です。  
  
## <a name="deploying-a-solution-by-using-windows-installer"></a>Windows インストーラーを使用したソリューションの配置  
 Windows インストーラーを使用してソリューションを配置するときは、ユーザーにセットアップ プログラムを配布し、ユーザーがそのプログラムを使用してソリューションをインストールします。 セットアップ プログラムを使用すると、現在のユーザーのみではなく、コンピューターのすべてのユーザーに同時にソリューションをインストールできます。 また、ユーザーがソリューションをインストールするときに表示されるオプションを、少し詳細に制御できます。 たとえば、使用許諾契約を表示したり、ユーザーがソリューションの特定のコンポーネントをインストールできるようにしたりすることができます。 ただし、ソリューションを更新する場合は、新しいセットアップ プログラムを配布する必要があります。 参照してください[Windows インストーラーを使用した Office ソリューションの配置](../vsto/deploying-an-office-solution-by-using-windows-installer.md)です。  
  
## <a name="see-also"></a>関連項目  
 [Office ソリューションのセキュリティ保護](../vsto/securing-office-solutions.md)   
 [ClickOnce を使用して Office ソリューションの配置](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Windows インストーラーを使用した Office ソリューションの配置](../vsto/deploying-an-office-solution-by-using-windows-installer.md)   
 [Office ソリューション配置のトラブルシューティング](../vsto/troubleshooting-office-solution-deployment.md)  
  
  