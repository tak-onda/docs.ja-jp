---
title: '方法: パネルの OnRender メソッドをオーバーライドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
ms.openlocfilehash: cefeee320e10a9e9de0d38894d4d865ca2e639ec
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368954"
---
# <a name="how-to-override-the-panel-onrender-method"></a>方法: パネルの OnRender メソッドをオーバーライドする
この例は、オーバーライドする方法を示します、<xref:System.Windows.Controls.Panel.OnRender%2A>メソッドの<xref:System.Windows.Controls.Panel>レイアウト要素にカスタムのグラフィカルな効果を追加するためにします。  
  
## <a name="example"></a>例  
 使用して、<xref:System.Windows.Controls.Panel.OnRender%2A>表示パネル要素にグラフィック効果を追加するにはメソッドです。 たとえば、このメソッドを使用すると、カスタム境界線や背景の効果を追加します。 A<xref:System.Windows.Media.DrawingContext>オブジェクトは、図形、テキスト、画像、またはビデオを描画するためのメソッドを提供する引数として渡されます。 その結果、このメソッドは、パネル オブジェクトのカスタマイズに役立ちます。  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a>関連項目
- <xref:System.Windows.Controls.Panel>
- [パネルの概要](panels-overview.md)
- [カスタム放射状パネルのサンプル](https://go.microsoft.com/fwlink/?LinkID=159982)
- [方法トピック](panel-how-to-topics.md)
