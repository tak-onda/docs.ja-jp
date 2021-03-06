---
title: '方法: Visual Basic では、StringBuilder を使用して文字列を作成します。'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 5cd118ddd196bdf84045ae8b02fe590e5b087e4e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967959"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>方法: Visual Basic では、StringBuilder を使用して文字列を作成します。
この例を使用して多数の小さな文字列から長い文字列を構築します、<xref:System.Text.StringBuilder>クラス。 <xref:System.Text.StringBuilder>クラスより効率的、`&=`演算子の多くの文字列を連結します。  
  
## <a name="example"></a>例  
 次の例のインスタンスを作成する、<xref:System.Text.StringBuilder>クラス、1,000 の文字列をそのインスタンスに追加し、その文字列表現を返します。  
  
 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]  
  
## <a name="see-also"></a>関連項目
- [StringBuilder クラスの使用](../../../../standard/base-types/stringbuilder.md)
- [& = 演算子](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [文字列](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [新しい文字列の作成](../../../../standard/base-types/creating-new.md)
- [文字列の操作](../../../../standard/base-types/manipulating-strings.md)
