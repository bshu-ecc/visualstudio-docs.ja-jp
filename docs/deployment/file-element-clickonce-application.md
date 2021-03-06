---
title: "&lt;ファイル&gt;要素 (ClickOnce アプリケーション) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://www.w3.org/2000/09/xmldsig#Transform
- urn:schemas-microsoft-com:asm.v2#file
- http://www.w3.org/2000/09/xmldsig#DigestValue
- http://www.w3.org/2000/09/xmldsig#DigestMethod
- http://www.w3.org/2000/09/xmldsig#Transforms
- urn:schemas-microsoft-com:asm.v2#hash
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <file> element [ClickOnce application manifest]
- manifests [ClickOnce], file element
ms.assetid: 56e3490c-eed5-4841-b1bf-eefe778b6ac9
caps.latest.revision: "24"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: f448b7455bcbe13b7257a58a0eafbadd1165b197
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2017
---
# <a name="ltfilegt-element-clickonce-application"></a>&lt;ファイル&gt;要素 (ClickOnce アプリケーション)
アセンブリ以外のファイルをすべてダウンロードして、アプリケーションで使用されるを識別します。  
  
## <a name="syntax"></a>構文  
  
```  
<file  
    name  
    size  
    group  
    optional  
    writeableType  
>  
    <typelib  
        tlbid  
        version  
        helpdir  
        resourceid  
        flags  
    />  
    <comClass  
        clsid  
        description  
        threadingModel  
        tlbid  
        progid  
        miscStatus  
        miscStatusIcon  
        miscStatusContent  
        miscStatusDocPrint  
        miscStatusThumbnail  
    />  
    <comInterfaceExternalProxyStub  
        iid  
        baseInterface  
        numMethods  
        name  
        tlbid  
        proxyStubClass32  
    />  
    <comInterfaceProxyStub  
        iid  
        baseInterface  
        numMethods  
        name  
        tlbid  
        proxyStubClass32  
    />  
    <windowClass  
        versioned  
    />  
</file>  
```  
  
## <a name="elements-and-attributes"></a>要素と属性  
 `file` 要素は省略可能です。 要素には、次の属性があります。  
  
|属性|説明|  
|---------------|-----------------|  
|`name`|必須です。 ファイルの名前を識別します。|  
|`size`|必須です。 ファイルのバイト単位のサイズを指定します。|  
|`group`|場合、省略可能、`optional`属性の指定またはに設定されていない`false`; 場合は必須`optional`は`true`します。 このファイルが属するグループの名前。 名前は、開発者が選択した任意の Unicode 文字列値を指定できを使用して必要に応じてファイルをダウンロードするために使用、<xref:System.Deployment.Application.ApplicationDeployment>クラスです。|  
|`optional`|省略可能です。 このファイルである必要があるかどうか、アプリケーションが最初にダウンロードを実行、または要求時に、アプリケーションが要求されるまでサーバー上でのみに存在する必要があります、ファイルのかどうか指定します。 場合`false`または定義されていないファイルをダウンロードするアプリケーションが最初に実行またはインストールされているときにします。 場合`true`、`group`を有効にするアプリケーション マニフェストを指定する必要があります。 `optional`true にすることはできない場合`writeableType`値で指定された`applicationData`です。|  
|`writeableType`|省略可能です。 このファイルは、データ ファイルを指定します。 現在、唯一の有効な値は`applicationData`します。|  
  
## <a name="typelib"></a>タイプ ライブラリ  
 `typelib`要素は、ファイルの要素のオプションの子です。 要素には、COM コンポーネントが属しているタイプ ライブラリがについて説明します。 要素には、次の属性があります。  
  
|属性|説明|  
|---------------|-----------------|  
|`tlbid`|必須です。 タイプ ライブラリに割り当てられた GUID です。|  
|`version`|必須です。 タイプ ライブラリのバージョン番号。|  
|`helpdir`|必須です。 コンポーネントのヘルプ ファイルを格納するディレクトリ。 長さゼロがあります。|  
|`resourceid`|省略可能です。 ロケール識別子 (LCID) の 16 進数の文字列形式。 これは、0 x プレフィックスなし、先行ゼロのない 16 進数、1 ~ 4 です。 LCID は、ニュートラル サブ言語識別子があります。|  
|`flags`|省略可能です。 このタイプ ライブラリのタイプ ライブラリ フラグの文字列形式。 具体的には、"RESTRICTED"、「コントロール」、"HIDDEN"および"HASDISKIMAGE"のいずれかを指定にする必要があります。|  
  
## <a name="comclass"></a>comClass  
 `comClass`要素の省略可能な子では、`file`要素が必要な場合は、[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]アプリケーションには、登録を必要としない COM を使用して展開する予定の COM コンポーネントが含まれています。 要素には、次の属性があります。  
  
|属性|説明|  
|---------------|-----------------|  
|`clsid`|必須です。 GUID として表される COM コンポーネントのクラス ID。|  
|`description`|省略可能です。 クラス名。|  
|`threadingModel`|省略可能です。 インプロセス COM クラスによって使用されるスレッド モデルです。 このプロパティが null の場合は、スレッド処理モデルは使用されません。 コンポーネントは、クライアントのメイン スレッドで作成され、他のスレッドからの呼び出しは、このスレッドにマーシャ リングします。 次に、有効な値を示します。<br /><br /> `Apartment`、`Free`、`Both`、および `Neutral`。|  
|`tlbid`|省略可能です。 この COM コンポーネントのタイプ ライブラリの GUID です。|  
|`progid`|省略可能です。 バージョンに依存する COM コンポーネントに関連付けられているプログラム id。 形式、`ProgID`は`<vendor>.<component>.<version>`します。|  
|`miscStatus`|省略可能です。 アセンブリ内の重複マニフェストによって提供される情報、`MiscStatus`レジストリ キー。 場合の値を`miscStatusIcon`、 `miscStatusContent`、 `miscStatusDocprint`、または`miscStatusThumbnail`属性が見つからない場合は、対応する既定値が記載`miscStatus`して足りない属性を使用します。 値は、次の表の属性値のコンマ区切りの一覧を指定できます。 COM クラスが必要とする OCX クラスの場合は、この属性を使用して`MiscStatus`レジストリ キーの値。|  
|`miscStatusIcon`|省略可能です。 アセンブリ内の重複はマニフェスト DVASPECT_ICON によって提供される情報です。 オブジェクトのアイコンを提供できます。 値は、次の表の属性値のコンマ区切りの一覧を指定できます。 COM クラスが必要とする OCX クラスの場合は、この属性を使用して`Miscstatus`レジストリ キーの値。|  
|`miscStatusContent`|省略可能です。 アセンブリ内の重複はマニフェスト DVASPECT_CONTENT によって提供される情報です。 画面またはプリンターの表示可能な複合ドキュメントを提供できます。 値は、次の表の属性値のコンマ区切りの一覧を指定できます。 COM クラスが必要とする OCX クラスの場合は、この属性を使用して`MiscStatus`レジストリ キーの値。|  
|`miscStatusDocPrint`|省略可能です。 アセンブリ内の重複はマニフェスト DVASPECT_DOCPRINT によって提供される情報です。 プリンターに印刷される場合に画面に表示可能なオブジェクト表現を提供できます。 値は、次の表の属性値のコンマ区切りの一覧を指定できます。 COM クラスが必要とする OCX クラスの場合は、この属性を使用して`MiscStatus`レジストリ キーの値。|  
|`miscStatusThumbnail`|省略可能です。 アセンブリ内の重複はマニフェスト DVASPECT_THUMBNAIL で提供される情報です。 参照ツールで表示可能なオブジェクトのサムネイルを提供できます。 値は、次の表の属性値のコンマ区切りの一覧を指定できます。 COM クラスが必要とする OCX クラスの場合は、この属性を使用して`MiscStatus`レジストリ キーの値。|  
  
## <a name="cominterfaceexternalproxystub"></a>comInterfaceExternalProxyStub  
 `comInterfaceExternalProxyStub`要素の省略可能な子では、`file`要素が場合に必要な可能性があります、[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]アプリケーションには、登録を必要としない COM を使用して展開する予定の COM コンポーネントが含まれています。 要素には、次の属性が含まれています。  
  
|属性|説明|  
|---------------|-----------------|  
|`iid`|必須です。 インターフェイス ID (IID) はこのプロキシによって処理されます。 IID には、中かっこで囲む必要があります。|  
|`baseInterface`|省略可能です。 インターフェイスが参照元となるインターフェイスの IID`iid`が派生します。|  
|`numMethods`|省略可能です。 インターフェイスによって実装されるメソッドの数。|  
|`name`|省略可能です。 インターフェイスの名前は、コードに表示されます。|  
|`tlbid`|省略可能です。 指定されたインターフェイスの説明を格納するタイプ ライブラリ、`iid`属性。|  
|`proxyStubClass32`|省略可能です。 32 ビット プロキシ Dll の CLSID に IID を割り当てます。|  
  
## <a name="cominterfaceproxystub"></a>comInterfaceProxyStub  
 `comInterfaceProxyStub`要素の省略可能な子では、`file`要素が場合に必要な可能性があります、[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]アプリケーションには、登録を必要としない COM を使用して展開する予定の COM コンポーネントが含まれています。 要素には、次の属性が含まれています。  
  
|属性|説明|  
|---------------|-----------------|  
|`iid`|必須です。 インターフェイス ID (IID) はこのプロキシによって処理されます。 IID には、中かっこで囲む必要があります。|  
|`baseInterface`|省略可能です。 インターフェイスが参照元となるインターフェイスの IID`iid`が派生します。|  
|`numMethods`|省略可能です。 インターフェイスによって実装されるメソッドの数。|  
|`Name`|省略可能です。 インターフェイスの名前は、コードに表示されます。|  
|`Tlbid`|省略可能です。 指定されたインターフェイスの説明を格納するタイプ ライブラリ、`iid`属性。|  
|`proxyStubClass32`|省略可能です。 32 ビット プロキシ Dll の CLSID に IID を割り当てます。|  
|`threadingModel`|省略可能です。 省略可能です。 インプロセス COM クラスによって使用されるスレッド モデルです。 このプロパティが null の場合は、スレッド処理モデルは使用されません。 コンポーネントは、クライアントのメイン スレッドで作成され、他のスレッドからの呼び出しは、このスレッドにマーシャ リングします。 次に、有効な値を示します。<br /><br /> `Apartment`、`Free`、`Both`、および `Neutral`。|  
  
## <a name="windowclass"></a>windowClass  
 `windowClass`要素の省略可能な子では、`file`要素が場合に必要な可能性があります、[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]アプリケーションには、登録を必要としない COM を使用して展開する予定の COM コンポーネントが含まれています。 要素は、対象となるバージョンが必要な COM コンポーネントで定義されたウィンドウ クラスを参照します。 要素には、次の属性が含まれています。  
  
|属性|説明|  
|---------------|-----------------|  
|`versioned`|省略可能です。 ウィンドウ クラスを含むアセンブリのバージョンを含む内部ウィンドウ クラスの登録で使用されているかどうかを制御します。 この属性の値を指定できます`yes`または`no`です。 既定値は、`yes` です。 値`no`サイド バイ サイド コンポーネントと同等の非--バイ サイド コンポーネントによって、同じウィンドウ クラスが定義されているし、同じウィンドウ クラスとして扱われるようにする場合にのみ使用する必要があります。 ウィンドウ クラスの登録に関する通常の規則が適用されるに注意してください: 対象となるバージョンがあるないために、ウィンドウ クラスを登録する最初のコンポーネントが、それを登録することにのみです。|  
  
## <a name="hash"></a>hash  
 `hash`要素の省略可能な子では、`file`要素。 `hash`要素に属性がありません。  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]展開後に変更されたファイルがないことを確認するのには、セキュリティ チェックとして、アプリケーション内のすべてのファイルのアルゴリズムのハッシュを使用します。 場合、`hash`要素が含まれていない、このチェックは実行されません。 そのため、省略すると、`hash`要素はお勧めしません。  
  
 そのマニフェストをデジタルにすることはできませんが、マニフェストにハッシュされていないファイルが含まれている場合のユーザーは、ハッシュされていないファイルの内容を確認できないため、署名します。  
  
## <a name="dsigtransforms"></a>dsig:Transforms  
 `dsig:Transforms`要素の必須の子では、`hash`要素。 `dsig:Transforms`要素に属性がありません。  
  
## <a name="dsigtransform"></a>dsig:Transform  
 `dsig:Transform`要素の必須の子では、`dsig:Transforms`要素。 `dsig:Transform`要素には、次の属性です。  
  
|属性|説明|  
|---------------|-----------------|  
|`Algorithm`|このファイルのダイジェストを計算するために使用するアルゴリズムです。 現在、唯一の値で使用される[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]は`urn:schemas-microsoft-com:HashTransforms.Identity`します。|  
  
## <a name="dsigdigestmethod"></a>dsig:DigestMethod  
 `dsig:DigestMethod`要素の必須の子では、`hash`要素。 `dsig:DigestMethod`要素には、次の属性です。  
  
|属性|説明|  
|---------------|-----------------|  
|`Algorithm`|このファイルのダイジェストを計算するために使用するアルゴリズムです。 現在、唯一の値で使用される[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]は`http://www.w3.org/2000/09/xmldsig#sha1`します。|  
  
## <a name="dsigdigestvalue"></a>目的  
 `dsig:DigestValue`要素の必須の子では、`hash`要素。 `dsig:DigestValue`要素に属性がありません。 テキスト値は、指定したファイルの計算されたハッシュです。  
  
## <a name="remarks"></a>コメント  
 この要素は、アプリケーションを構成するすべてのアセンブリ以外のファイルを識別し、具体的には、検証のファイルのハッシュ値。 この要素は、ファイルに関連付けられているコンポーネント オブジェクト モデル (COM) 分離データを含めることもできます。 ファイルが変更された場合、アプリケーション マニフェスト ファイルも変更を反映するように更新する必要があります。  
  
## <a name="example"></a>例  
 次のコード例を示しています`file`アプリケーション内の要素を使用してデプロイされたアプリケーションのマニフェストの[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]します。  
  
```  
<file name="Icon.ico" size="9216">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>lVoj+Rh6RQ/HPNLOdayQah5McrI=</dsig:DigestValue>  
  </hash>  
</file>  
```  
  
## <a name="see-also"></a>関連項目  
 [ClickOnce アプリケーション マニフェスト](../deployment/clickonce-application-manifest.md)