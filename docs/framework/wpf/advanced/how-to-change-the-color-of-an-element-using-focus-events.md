---
title: '方法: フォーカス イベントを使用して要素の色を変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: 0d2c297108da7af09e5f01551bdedc5f0ac5e9af
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361006"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a>方法: フォーカス イベントを使用して要素の色を変更する
この例を取得しを使用してフォーカスを失ったときに、要素の色を変更する方法を示しています、<xref:System.Windows.UIElement.GotFocus>と<xref:System.Windows.UIElement.LostFocus>イベント。  
  
 この例は、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ファイルと分離コード ファイル。  
  
## <a name="example"></a>例  
 次[!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]の 2 つで構成されるユーザー インターフェイスを作成します。<xref:System.Windows.Controls.Button>オブジェクト、およびイベント ハンドラーをアタッチします、<xref:System.Windows.UIElement.GotFocus>と<xref:System.Windows.UIElement.LostFocus>イベントを、<xref:System.Windows.Controls.Button>オブジェクト。  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 次のコードを作成、<xref:System.Windows.UIElement.GotFocus>と<xref:System.Windows.UIElement.LostFocus>イベント ハンドラー。  ときに、<xref:System.Windows.Controls.Button>キーボード フォーカスの向上、<xref:System.Windows.Controls.Control.Background%2A>の<xref:System.Windows.Controls.Button>赤に変更されます。  ときに、<xref:System.Windows.Controls.Button>がキーボード フォーカスを失う、<xref:System.Windows.Controls.Control.Background%2A>の<xref:System.Windows.Controls.Button>が白に変更します。  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a>関連項目
- [入力の概要](input-overview.md)
