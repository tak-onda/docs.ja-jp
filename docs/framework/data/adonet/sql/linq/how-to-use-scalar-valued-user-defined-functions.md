---
title: '方法: スカラー値ユーザー定義関数を使用して、'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
ms.openlocfilehash: 33c6ae89184b90ba69cc9c3c01f0b1ec9d7ff1cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661686"
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a>方法: スカラー値ユーザー定義関数を使用して、
<xref:System.Data.Linq.Mapping.FunctionAttribute> 属性を使用することによって、クラスで定義されているクライアント メソッドを、ユーザー定義関数に対応付けることができます。 メソッドの本体は、メソッド呼び出しの目的を反映する式を構築し、変換および実行のためにその式を <xref:System.Data.Linq.DataContext> に渡します。  
  
> [!NOTE]
>  直接実行は、関数がクエリの外部で呼び出される場合のみ発生します。 詳細については、「[方法 :ユーザー定義関数をインラインで呼び出す](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)します。  
  
## <a name="example"></a>例  
 次の SQL コードは、スカラー値のユーザー定義関数 `ReverseCustName()` を示しています。  
  
```  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 このコードで、次のようなクライアント メソッドを対応付けます。  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a>関連項目
- [ユーザー定義関数](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
