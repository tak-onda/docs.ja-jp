---
title: "'<typename>' はデリゲート型です。"
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 4278ea0fc6a8dc2c6a90b720d2da70b1c26f2a17
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283453"
---
# <a name="typename-is-a-delegate-type"></a>'\<typename>' はデリゲート型です。
'\<typename>' はデリゲート型です。 デリゲート構築では、引数リストとして 1 つの AddressOf 式のみを許可します。 多くの場合、デリゲート構築ではなく、AddressOf 式を使用できます。  
  
 デリゲート クラスのインスタンスを作成する`New`句で、デリゲート コンストラクタへの無効な引数リストが指定されています。  
  
 デリゲート インスタンスを新規作成するときは、単一の`AddressOf`式しか指定できません。  
  
 このエラーは、デリゲート コンストラクターへ引数を 1 つも渡していない場合、複数の引数を渡している場合、または有効な`AddressOf`式ではない 1 つの引数を渡している場合に発生する可能性があります。  
  
 **エラー ID:** BC32008  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   `New`句で、デリゲート クラスの引数リストに単一の`AddressOf`式を使用します。  
  
## <a name="see-also"></a>関連項目
- [New 演算子](../../../visual-basic/language-reference/operators/new-operator.md)
- [AddressOf 演算子](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [デリゲート](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [方法: デリゲート メソッドを呼び出す](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
