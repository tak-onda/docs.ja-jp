---
title: 手書き認識
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handwriting recognition [WPF]
- recognition of handwriting [WPF]
ms.assetid: f4e8576d-e731-4bac-9818-22e2ae636636
ms.openlocfilehash: 08cd9e0a167d1bef9bbe6437b22985082c80e5f9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365803"
---
# <a name="handwriting-recognition"></a>手書き認識
このセクションでは、WPF プラットフォームのデジタル インクに関連する認識の基礎について説明します。  
  
## <a name="recognition-solutions"></a>認識ソリューション  
 次の例は、[Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) クラスを利用し、インクを認識する方法を示しています。  
  
> [!NOTE]
>  このサンプルでは、手書き認識エンジンをインストールする必要があります。  
  
 Visual Studio で **InkRecognition** という名前の新しい WPF アプリケーション プロジェクトを作成します。 Window1.xaml ファイルの内容を次の XAML コードに置き換えます。 このコードにより、アプリケーションのユーザー インターフェイスがレンダリングされます。  
  
 [!code-xaml[InkRecognition#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 Microsoft インク アセンブリである Microsoft.Ink.dll に参照を追加します。これは Program Files\Common Files\Microsoft Shared\Ink にあります。 この分離コード ファイルの内容を次のコードで置き換えます。  
  
 [!code-csharp[InkRecognition#2](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>関連項目
- [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))
