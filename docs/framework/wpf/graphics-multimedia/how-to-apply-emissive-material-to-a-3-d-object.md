---
title: '方法: 3-D モデルに放射性素材を適用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3-D objects
- 3-D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: 7f4158d59334c2f80775541ea1b0f944e048b081
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362501"
---
# <a name="how-to-apply-emissive-material-to-a-3-d-object"></a>方法: 3-D モデルに放射性素材を適用する
次の例は、使用する方法を示します<xref:System.Windows.Media.Media3D.EmissiveMaterial>EmissiveMaterial のブラシの色に等しい既存の材料に色を追加します。 次のコード<xref:System.Windows.Media.Media3D.DiffuseMaterial>と<xref:System.Windows.Media.Media3D.EmissiveMaterial>DiffuseMaterial の外観に青色を追加するための組み合わせに適用します。  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 手続き型コード。  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a>例  
 次のコードでは、XAML でサンプル全体を示しています。  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a>例  
 以下の手続き型コード全体のサンプルに示します。  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a>関連項目
- [3-D シーンを作成する](how-to-create-a-3-d-scene.md)
- [3-D グラフィックスの概要](3-d-graphics-overview.md)
- [3-D シーンで素材プロパティをアニメーション化する](how-to-animate-material-properties-in-a-3-d-scene.md)
- [3-D オブジェクトの前面および背面に素材を適用する](how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
