---
title: '方法: 自動レイアウトを使用してボタンを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 2172aba80fe963be33036a7245f228e8d5bfedda
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370346"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a>方法: 自動レイアウトを使用してボタンを作成する
この例では、自動レイアウトの方法を使用して、ローカライズ可能なアプリケーションにボタンを作成する方法について説明します。  
  
 ローカライズ、[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]時間がかかることができます。 多くの場合、ローカライザーは、テキストの翻訳だけでなく、要素のサイズ変更や位置変更を行う必要があります。 過去の各言語を[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]が必要な調整を変更します。 機能を今すぐ[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]調整の必要性が軽減される要素を設計することができます。 簡単にサイズ変更や位置が変更された可能性のあるアプリケーションの作成方法と呼びます`automatic layout`します。  
  
 次の 2 つ[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]の例は、ボタン; スペイン語のテキストのいずれかと英語のテキストを 1 つのインスタンスを作成するアプリケーションを作成します。 テキストを除き、コードは同じであることに注目してください。ボタンがテキストに合わせて調整されます。  
  
## <a name="example"></a>例  
 [!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 [!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 次の図は、コード サンプルの出力を示しています。  
  
 ![テキストの言語が異なる同じボタン](./media/globalizationbutton.png "GlobalizationButton")  
自動サイズ変更可能なボタン  
  
## <a name="see-also"></a>関連項目
- [自動レイアウトの使用の概要](use-automatic-layout-overview.md)
- [自動レイアウト用のグリッドを使用する](how-to-use-a-grid-for-automatic-layout.md)
