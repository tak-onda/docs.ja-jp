---
title: '方法: PointAnimation を使用してオブジェクトの位置をアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: 04dbcfdb64525e6231ecf33c8ac5ecf2a2d2cb7e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357933"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a>方法: PointAnimation を使用してオブジェクトの位置をアニメーション化する
この例は、使用する方法を示します、<xref:System.Windows.Media.Animation.PointAnimation>に沿ってオブジェクトをアニメーション化するクラス、<xref:System.Windows.Shapes.Path>します。  
  
## <a name="example"></a>例  
 次の例に沿って楕円を移動する、<xref:System.Windows.Shapes.Path>別の画面に 1 つのポイントから。 この例の位置をアニメーション化、<xref:System.Windows.Media.EllipseGeometry>を使用して<xref:System.Windows.Media.Animation.PointAnimation>をアニメーション化する、<xref:System.Windows.Media.EllipseGeometry.Center%2A>プロパティ。  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a>関連項目
- <xref:System.Windows.Media.Animation.PointAnimation>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.EllipseGeometry>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A>
- [アニメーションの概要](animation-overview.md)
- [グラフィックスとマルチメディア](index.md)
- [グラフィックスの操作方法に関するトピック](graphics-how-to-topics.md)
- [アニメーションとタイミングに関するトピック](animation-and-timing-how-to-topics.md)
