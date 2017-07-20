---
title: "ツール ウィンドウのショートカット メニューを追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- context menus, adding to tool windows
- menus, context menus
- shortcut menus, adding to tool windows
- tool windows, adding context menus
ms.assetid: 50234537-9e95-4b7e-9cb7-e5cf26d6e9d2
caps.latest.revision: 37
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
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: ab921bec73528be7207baebdf9cb31885e2253fd
ms.lasthandoff: 02/22/2017

---
# <a name="adding-a-shortcut-menu-in-a-tool-window"></a>ツール ウィンドウのショートカット メニューを追加します。
このチュートリアルでは、ツール ウィンドウのショートカット メニューを配置します。 ショートカット メニューは、ユーザーは、ボタン、テキスト ボックスまたはウィンドウの背景を右クリックしたときに表示されるメニューです。 ショートカット メニューのコマンドは、その他のメニューまたはツールバーでコマンドと同様に動作します。 ショートカット メニューをサポートするために .vsct ファイルで指定し、マウスの右クリックに応答に表示します。  
  
 ツール ウィンドウは、 <xref:Microsoft.VisualStudio.Shell.ToolWindowPane>。</xref:Microsoft.VisualStudio.Shell.ToolWindowPane>から継承するカスタム ツール ウィンドウ クラス内の WPF ユーザー コントロールで構成されています  
  
 このチュートリアルでは、.vsct ファイルでのメニュー項目を宣言し、ツール ウィンドウを定義するクラスで実装するパッケージの管理フレームワークを使用して Visual Studio のメニューにショートカット メニューを作成する方法を示します。 このアプローチには、Visual Studio のコマンド、UI 要素、およびオートメーション オブジェクト モデルへのアクセスが容易になります。  
  
 または、ショートカット メニューでは、Visual Studio の機能はアクセスできませんが、参照して、<xref:System.Windows.FrameworkElement.ContextMenu%2A>ユーザー コントロール内の XAML 要素のプロパティ</xref:System.Windows.FrameworkElement.ContextMenu%2A>。 詳細については、次を参照してください。 [ContextMenu](http://msdn.microsoft.com/Library/2f40b2bb-b702-4706-9fc4-10bcfd7cc35d)します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 Visual Studio 2015 以降、インストールしない、Visual Studio SDK ダウンロード センターからです。 Visual Studio のセットアップのオプション機能として含まれます。 後で、VS SDK をインストールすることもできます。 詳細については、次を参照してください。 [Visual Studio SDK をインストールする](../extensibility/installing-the-visual-studio-sdk.md)です。  
  
## <a name="creating-the-tool-window-shortcut-menu-package"></a>ツール ウィンドウのショートカット メニューのパッケージを作成します。  
  
1.  という名前の VSIX プロジェクトを作成する`TWShortcutMenu`という名前のツール ウィンドウ テンプレートを追加および**ショートカット メニュー**にします。 ツール ウィンドウの作成の詳細については、次を参照してください。[ツール ウィンドウで、拡張機能を作成する](../extensibility/creating-an-extension-with-a-tool-window.md)です。  
  
## <a name="specifying-the-shortcut-menu"></a>ショートカット メニューを指定します。  
 このチュートリアルで示すように&1; つにより、ユーザーなどのショートカット メニューは、ツール ウィンドウの背景の塗りつぶしに使用される色の一覧から選択します。  
  
1.  ShortcutMenuPackage.vsct で GuidSymbol 要素 guidShortcutMenuPackageCmdSet、という名前で検索し、ショートカット メニューのショートカット メニューのグループ、およびメニュー オプションを宣言します。 GuidSymbol 要素は、次のようになります。  
  
    ```xml  
    <GuidSymbol name="guidShortcutMenuPackageCmdSet" value="{00000000-0000-0000-0000-0000}"> // your GUID here  
        <IDSymbol name="ShortcutMenuCommandId" value="0x0100" />  
        <IDSymbol name="ColorMenu" value="0x1000"/>  
        <IDSymbol name="ColorGroup" value="0x1100"/>  
        <IDSymbol name="cmdidRed" value="0x102"/>  
        <IDSymbol name="cmdidYellow" value="0x103"/>  
        <IDSymbol name="cmdidBlue" value="0x104"/>  
    </GuidSymbol>  
    ```  
  
2.  ボタンの要素の直前にメニュー要素を作成し、これで、ショートカット メニューを定義します。  
  
    ```vb  
    <Menus>  
      <Menu guid="guidShortcutMenuPackageCmdSet" id="ColorMenu" type="Context">  
        <Strings>  
          <ButtonText>Color change</ButtonText>  
          <CommandName>ColorChange</CommandName>  
        </Strings>  
      </Menu>  
    </Menus>  
    ```  
  
     メニューまたはツールバーの一部ではないために、ショートカット メニューは、親がありません。  
  
3.  ショートカット メニュー アイテムを含むグループ要素を持つグループ要素を作成し、ショートカット メニューで、グループを関連付けます。  
  
    ```xml  
    <Groups>  
        <Group guid="guidShortcutMenuPackageCmdSet" id="ColorGroup">  
            <Parent guid="guidShortcutMenuPackageCmdSet" id="ColorMenu"/>  
        </Group>  
    </Groups>  
    ```  
  
4.  ボタンの要素では、ショートカット メニューに表示される個々 のコマンドを定義します。 ボタンの要素は、次のようになります。  
  
    ```xml  
    <Buttons>  
        <Button guid="guidShortcutMenuPackageCmdSet" id="ShortcutMenuCommandId" priority="0x0100" type="Button">  
            <Parent guid="guidSHLMainMenu" id="IDG_VS_WNDO_OTRWNDWS1"/>  
            <Icon guid="guidImages" id="bmpPic1" />  
            <Strings>  
                <ButtonText>ShortcutMenu</ButtonText>  
            </Strings>  
        </Button>  
  
        <Button guid="guidShortcutMenuPackageCmdSet" id="cmdidRed" priority="1" type="Button">  
            <Parent guid="guidShortcutMenuPackageCmdSet" id="ColorGroup" />  
            <Strings>  
                <ButtonText>Red</ButtonText>  
            </Strings>  
        </Button>  
  
        <Button guid="guidShortcutMenuPackageCmdSet" id="cmdidYellow" priority="3" type="Button">  
            <Parent guid="guidShortcutMenuPackageCmdSet" id="ColorGroup" />  
            <Strings>  
                <ButtonText>Yellow</ButtonText>  
            </Strings>  
        </Button>  
  
        <Button guid="guidShortcutMenuPackageCmdSet" id="cmdidBlue" priority="5" type="Button">  
            <Parent guid="guidShortcutMenuPackageCmdSet" id="ColorGroup" />  
            <Strings>  
                <ButtonText>Blue</ButtonText>  
            </Strings>  
        </Button>  
    </Buttons>  
    ```  
  
5.  ShortcutMenuPackageGuids.cs、コマンドの定義セット GUID、ショートカット メニューおよびメニュー項目を追加します。  
  
    ```c#  
    public const string guidShortcutMenuPackageCmdSet = "00000000-0000-0000-0000-00000000"; // your GUID will differ  
    public const int ColorMenu = 0x1000;  
    public const int cmdidRed = 0x102;  
    public const int cmdidYellow = 0x103;  
    public const int cmdidBlue = 0x104;  
    ```  
  
     これらは、ShortcutMenuPackage.vsct ファイルの Symbols セクションで定義されている同じコマンド Id です。 コンテキストのグループは含まれませんここ .vsct ファイルでのみ必要なためです。  
  
## <a name="implementing-the-shortcut-menu"></a>ショートカット メニューを実装します。  
 このセクションでは、ショートカット メニューのおよびコマンドを実装します。  
  
1.  ShortcutMenu.cs、ツール ウィンドウ、メニュー コマンドのサービスを取得できますが、コントロールが含まれていることはできません。 次の手順では、メニュー コマンドのサービスをユーザー コントロールを使用できるようにする方法を示します。  
  
2.  次のコードを追加、ShortcutMenu.cs でステートメントを使用します。  
  
    ```c#  
    using Microsoft.VisualStudio.Shell;  
    using System.ComponentModel.Design;  
    ```  
  
3.  メニュー コマンドのサービスを取得し、メニュー コマンドのサービスをコンス トラクターに渡すコントロールを追加するツール ウィンドウの Initialize() メソッドをオーバーライドします。  
  
    ```c#  
    protected override void Initialize()  
    {  
        commandService = (OleMenuCommandService)GetService(typeof(IMenuCommandService));  
        Content = new ShortcutMenuControl(commandService);  
    }  
    ```  
  
4.  ショートカット メニューのツール ウィンドウ コンス トラクターでは、コントロールを追加する行を削除します。 コンス トラクターは、次のようになります。  
  
    ```c#  
    public ShortcutMenu() : base(null)  
    {  
        this.Caption = "ShortcutMenu";  
        this.BitmapResourceID = 301;  
        this.BitmapIndex = 1;  
    }  
    ```  
  
5.  ShortcutMenuControl.xaml.cs、メニュー コマンドのサービスのプライベート フィールドを追加し、メニュー コマンドのサービスを実行するコントロールのコンス トラクターを変更します。 メニュー コマンドのサービスを使用してをコンテキスト メニューのコマンドを追加します。 ShortcutMenuControl コンス トラクターは、次のようになります。 コマンド ハンドラーは、後で定義されます。  
  
    ```c#  
    public ShortcutMenuControl(OleMenuCommandService service)  
    {  
        this.InitializeComponent();  
        commandService = service;  
  
        if (null !=commandService)  
        {  
            // Create an alias for the command set guid.  
            Guid guid = new Guid(ShortcutMenuPackageGuids.guidShortcutMenuPackageCmdSet);  
  
            // Create the command IDs.   
            var red = new CommandID(guid, ShortcutMenuPackageGuids.cmdidRed);  
            var yellow = new CommandID(guid, ShortcutMenuPackageGuids.cmdidYellow);  
            var blue = new CommandID(guid, ShortcutMenuPackageGuids.cmdidBlue);  
  
            // Add a command for each command ID.  
            commandService.AddCommand(new MenuCommand(ChangeColor, red));  
            commandService.AddCommand(new MenuCommand(ChangeColor, yellow));  
            commandService.AddCommand(new MenuCommand(ChangeColor, blue));  
        }  
    }  
    ```  
  
6.  ShortcutMenuControl.xaml で追加、<xref:System.Windows.UIElement.MouseRightButtonDown>最上位レベルにイベント<xref:System.Windows.Controls.UserControl>要素</xref:System.Windows.Controls.UserControl></xref:System.Windows.UIElement.MouseRightButtonDown>。 XAML ファイルが次のようになります。  
  
    ```vb  
    <UserControl x:Class="TWShortcutMenu.ShortcutMenuControl"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
            Background="{DynamicResource VsBrush.Window}"  
            Foreground="{DynamicResource VsBrush.WindowText}"  
            mc:Ignorable="d"  
            d:DesignHeight="300" d:DesignWidth="300"  
            Name="MyToolWindow"  
            MouseRightButtonDown="MyToolWindow_MouseRightButtonDown">  
        <Grid>  
            <StackPanel Orientation="Vertical">  
                <TextBlock Margin="10" HorizontalAlignment="Center">ShortcutMenu</TextBlock>  
            </StackPanel>  
        </Grid>  
    </UserControl>  
    ```  
  
7.  ShortcutMenuControl.xaml.cs では、イベント ハンドラーのスタブを追加します。  
  
    ```c#  
    private void MyToolWindow_MouseRightButtonDown(object sender, MouseButtonEventArgs e)  
    {  
    . . .  
    }  
    ```  
  
8.  次の追加 using ステートメントを同じファイル。  
  
    ```c#  
    using Microsoft.VisualStudio.Shell;  
    using System.ComponentModel.Design;  
    using System;  
    using System.Windows.Input;  
    using System.Windows.Media;  
    ```  
  
9. 実装、`MyToolWindowMouseRightButtonDown`イベントを次のようにします。  
  
    ```c#  
    private void MyToolWindow_MouseRightButtonDown(object sender, MouseButtonEventArgs e)  
    {  
        if (null != commandService)  
        {  
            CommandID menuID = new CommandID(  
                new Guid(ShortcutMenuPackageGuids.guidShortcutMenuPackageCmdSet),  
                ShortcutMenuPackageGuids.ColorMenu);  
            Point p = this.PointToScreen(e.GetPosition(this));  
            commandService.ShowContextMenu(menuID, (int)p.X, (int)p.Y);  
        }  
    }  
    ```  
  
     こうと、<xref:System.ComponentModel.Design.CommandID>オブジェクトのショートカット メニューには、マウス クリックの場所が示されを使用してその場所でショートカット メニューを開き、<xref:Microsoft.VisualStudio.Shell.OleMenuCommandService.ShowContextMenu%2A>メソッド</xref:Microsoft.VisualStudio.Shell.OleMenuCommandService.ShowContextMenu%2A></xref:System.ComponentModel.Design.CommandID>。  
  
10. コマンド ハンドラーを実装します。  
  
    ```c#  
    private void ChangeColor(object sender, EventArgs e)  
    {  
        var mc = sender as MenuCommand;  
  
        switch (mc.CommandID.ID)  
        {  
            case ShortcutMenuPackageGuids.cmdidRed:  
                MyToolWindow.Background = Brushes.Red;  
                break;  
            case ShortcutMenuPackageGuids.cmdidYellow:  
                MyToolWindow.Background = Brushes.Yellow;  
                break;  
            case ShortcutMenuPackageGuids.cmdidBlue:  
                MyToolWindow.Background = Brushes.Blue;  
                break;  
        }  
    }  
    ```  
  
     1 つのメソッドが特定することによってメニュー項目のすべてのイベントを処理する場合は、<xref:System.ComponentModel.Design.CommandID>し、適切な背景色を設定します</xref:System.ComponentModel.Design.CommandID>。 メニュー項目には、関連のないコマンドが含まれていた場合、は、コマンドごとに個別のイベント ハンドラーを作成したとします。  
  
## <a name="testing-the-tool-window-features"></a>ツール ウィンドウの機能をテストします。  
  
1.  プロジェクトをビルドし、デバッグを開始します。 実験用インスタンスが表示されます。  
  
2.  実験用インスタンスで、クリックして**ビュー/その他のウィンドウ**、 をクリックし、**ショートカット メニュー**します。 これを行うと、ツール ウィンドウが表示されます。  
  
3.  ツール ウィンドウの本文で右クリックします。 色のリストを持つショートカット メニューを表示する必要があります。  
  
4.  ショートカット メニューの 色をクリックします。 ツール ウィンドウの背景色は、選択した色に変更する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [コマンド、メニューのおよびツールバー](../extensibility/internals/commands-menus-and-toolbars.md)   
 [使用して、サービスを提供します。](../extensibility/using-and-providing-services.md)