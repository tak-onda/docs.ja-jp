---
title: '方法: UI であるアドインを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: f81812b766242311ac29c43de68906d65ae52b32
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366388"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>方法: UI であるアドインを作成する
この例では、WPF のスタンドアロン アプリケーションでホストされている Windows Presentation Foundation (WPF) であるアドインを作成する方法を示します。  
  
 アドインの WPF ユーザー コントロールは、UI であります。 ユーザー コントロールの中身は 1 つのボタンであり、クリックすると、メッセージ ボックスを表示します。 スタンドアロンの WPF アプリケーションでは、アプリケーションのメイン ウィンドウの内容として、アドインの UI をホストします。  
  
 **必須コンポーネント**  
  
 この例では、このシナリオを有効にする、.NET Framework アドイン モデルを WPF 拡張を強調表示し、前提条件は次。  
  
-   .NET Framework アドイン モデルのパイプライン、アドイン、およびホストの開発を含むナレッジです。 これらの概念に慣れていない場合は、次を参照してください。[アドインおよび拡張](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))します。 パイプライン、アドイン、およびホスト アプリケーションの実装を示すチュートリアルについては、次を参照してください。[チュートリアル。拡張可能なアプリケーションを作成する](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))します。  
  
-   WPF の拡張機能を .NET Framework アドイン モデルの知識。 参照してください[WPF アドインの概要](wpf-add-ins-overview.md)します。  
  
## <a name="example"></a>例  
 WPF の UI は、アドインを作成するには、各パイプライン セグメント、アドイン、およびホスト アプリケーションの特定のコードが必要です。  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>コントラクト パイプライン セグメントの実装  
 アドインの UI である、ときに、アドインのコントラクトを実装する必要があります<xref:System.AddIn.Contract.INativeHandleContract>します。 例では、`IWPFAddInContract`実装<xref:System.AddIn.Contract.INativeHandleContract>、次のコードに示すようにします。  
  
 [!code-csharp[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]  
  
<a name="AddInViewPipeline"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>アドイン ビュー パイプライン セグメントの実装  
 アドインはのサブクラスとして実装されるため、<xref:System.Windows.FrameworkElement>アドイン ビューの種類はサブクラス化も必要<xref:System.Windows.FrameworkElement>します。 次のコードとして実装されるコントラクトのアドイン ビューを示しています、`WPFAddInView`クラス。  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
  
 ここでは、アドイン ビューがから派生した<xref:System.Windows.Controls.UserControl>します。 その結果、アドインの UI から派生する必要がありますも<xref:System.Windows.Controls.UserControl>します。  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>アドイン側アダプター パイプライン セグメントの実装  
 コントラクトは、 <xref:System.AddIn.Contract.INativeHandleContract>、アドインでは、 <xref:System.Windows.FrameworkElement> (アドイン ビュー パイプライン セグメントによって、指定した)。 そのため、<xref:System.Windows.FrameworkElement>に変換する必要があります、<xref:System.AddIn.Contract.INativeHandleContract>分離境界を越える前にします。 呼び出して追加アドイン側アダプターによってこの作業が実行される<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>、次のコードに示すようにします。  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
  
 アドインの UI を返すアドイン モデルで (を参照してください[UI を作成するアドインを返すこと](how-to-create-an-add-in-that-returns-a-ui.md))、アドイン アダプタの変換、<xref:System.Windows.FrameworkElement>を<xref:System.AddIn.Contract.INativeHandleContract>呼び出して<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>。 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> 必要があります呼び出すことも、このモデルでが、これを呼び出すコードを記述するメソッドを実装する必要があります。 オーバーライドすることで、これを行う<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>を呼び出すコードを実装して<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>場合を呼び出しているコード<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>が必要ですが、<xref:System.AddIn.Contract.INativeHandleContract>します。 この場合、呼び出し元はホスト側のアダプターであり、これについては、後で説明します。  
  
> [!NOTE]
>  オーバーライドする必要がありますも<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>ホスト アプリケーションの UI 間のタブ移動を有効にして、アドインの UI には、このモデルでします。 詳細については、「WPF アドインの制限」を参照してください[WPF アドインの概要](wpf-add-ins-overview.md)します。  
  
 追加アドイン側アダプターから派生するインターフェイスを実装するため、<xref:System.AddIn.Contract.INativeHandleContract>も実装する必要があります<xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>これは無視されますが、ときに<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>オーバーライドされます。  
  
<a name="HostViewPipeline"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>ホスト ビュー パイプライン セグメントの実装  
 このモデルで、ホスト アプリケーション通常はホスト ビューに、<xref:System.Windows.FrameworkElement>サブクラスです。 ホスト側アダプターに変換する必要があります、<xref:System.AddIn.Contract.INativeHandleContract>を<xref:System.Windows.FrameworkElement>後、<xref:System.AddIn.Contract.INativeHandleContract>分離境界を超えています。 メソッドを取得するホスト アプリケーションから呼び出されないされているため、 <xref:System.Windows.FrameworkElement>、ホスト ビュー返す必要があります""、<xref:System.Windows.FrameworkElement>格納することによって。 その結果、ホスト ビューのサブクラスから派生する必要があります<xref:System.Windows.FrameworkElement>他を含む[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]など<xref:System.Windows.Controls.UserControl>します。 次のコードとして実装されるコントラクトのホスト ビューを示しています、`WPFAddInHostView`クラス。  
  
  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>ホスト側アダプター パイプライン セグメントの実装  
 コントラクトは、 <xref:System.AddIn.Contract.INativeHandleContract>、ホスト アプリケーションでは、 <xref:System.Windows.Controls.UserControl> (ホスト ビューによって、指定した)。 その結果、<xref:System.AddIn.Contract.INativeHandleContract>に変換する必要があります、<xref:System.Windows.FrameworkElement>ホスト ビューのコンテンツとして設定される前に、分離境界を越えた後 (から派生した<xref:System.Windows.Controls.UserControl>)。  
  
 この作業は、次のコードに示されているように、ホスト側アダプターによって行われます。  
  
  
  
 ホスト側アダプターが取得、ご覧のとおり、<xref:System.AddIn.Contract.INativeHandleContract>呼び出して追加アドイン側アダプターの<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>メソッド (これは、ポイント場所、<xref:System.AddIn.Contract.INativeHandleContract>が分離境界を越える)。  
  
 ホスト側アダプターが次に、変換、<xref:System.AddIn.Contract.INativeHandleContract>を<xref:System.Windows.FrameworkElement>呼び出して<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>します。 最後に、<xref:System.Windows.FrameworkElement>ホスト ビューのコンテンツとして設定されます。  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>アドインの実装  
 アドイン側アダプターとアドイン ビューが用意できると、次のコードに示されているように、アドイン ビューから派生することでアドインを実装できます。  
  
  
  
  
  
 この例から、このモデルの 1 つの興味深い利点を確認できます。 アドイン開発者は、追加では、(UI もある) ためではなく、アドイン クラスとアドインの UI を実装するためにのみ必要があります。  
  
<a name="HostApp"></a>   
## <a name="implementing-the-host-application"></a>ホスト アプリケーションの実装  
 ホスト側アダプターとホスト ビューの作成、ホスト アプリケーションを使用できます、[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]アドイン モデルをパイプラインを開き、アドインのホスト ビューを取得します。 これらの手順を次のコードに示します。  
  
  
  
 ホスト アプリケーションでは、.NET Framework アドイン モデルの一般的なコードを使用して、アドイン、ホスト アプリケーションに暗黙的に、ホスト ビューを返しますアクティブにします。 ホスト アプリケーションは、その後、ホスト ビューを表示します (これは、 <xref:System.Windows.Controls.UserControl>) から、<xref:System.Windows.Controls.Grid>します。  
  
 アドインの UI との対話を処理するためのコードは、アドインのアプリケーション ドメインで実行されます。 このような対話には、次のようなものがあります。  
  
-   処理、 <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click>イベント。  
  
-   表示、<xref:System.Windows.MessageBox>します。  
  
 このアクティビティは、ホスト アプリケーションから完全に分離されています。  
  
## <a name="see-also"></a>関連項目
- [アドインおよび拡張機能](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [WPF のアドインの概要](wpf-add-ins-overview.md)
