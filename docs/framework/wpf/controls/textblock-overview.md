---
title: TextBlock の概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], TextBlock
- TextBlock control [WPF]
ms.assetid: 24720bca-341a-4b03-8a6b-7a678023b10a
ms.openlocfilehash: a3ea656a902f8a112a700667b6e08cae7463f68d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374467"
---
# <a name="textblock-overview"></a>TextBlock の概要
<xref:System.Windows.Controls.TextBlock>コントロールは、柔軟なテキスト サポートを提供します。[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーション。 この要素は、主として、複数段落のテキストを必要としない、基本的な [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] シナリオを対象にしています。 さまざまななどのプレゼンテーションでは、正確に制御を有効にするプロパティがサポートしている<xref:System.Windows.Controls.TextBlock.FontFamily%2A>、 <xref:System.Windows.Controls.TextBlock.FontSize%2A>、 <xref:System.Windows.Controls.TextBlock.FontWeight%2A>、 <xref:System.Windows.Controls.TextBlock.TextEffects%2A>、および<xref:System.Windows.Controls.TextBlock.TextWrapping%2A>します。 使用して、テキスト コンテンツを追加することができます、<xref:System.Windows.Controls.TextBlock.Text%2A>プロパティ。 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] で使用すると、オープン タグとクローズ タグの間の内容は、要素のテキストとして暗黙的に追加されます。  
  
 A<xref:System.Windows.Controls.TextBlock>要素は非常に単純を使用してインスタンス化できる[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]します。  
  
 [!code-xaml[TextBlockSnip_XAML#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip_XAML/CS/default.xaml#2)]  
  
 同様の使用状況、<xref:System.Windows.Controls.TextBlock>コード内の要素は比較的単純です。  
  
 [!code-csharp[TextBlockSnip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip/CSharp/TextBlockSnips.cs#1)]
 [!code-vb[TextBlockSnip#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBlockSnip/VisualBasic/TextBlockSnips.vb#1)]  
  
## <a name="see-also"></a>関連項目
- <xref:System.Windows.Controls.Label>
