---
title: '方法: 読み取り/書き込みのプロパティの宣言と使用 - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
ms.openlocfilehash: b4dc9364e64f7ebfd495671b852b98d8f56c80b5
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969035"
---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a>方法: 読み取り/書き込みのプロパティの宣言と使用 (C# プログラミング ガイド)
プロパティは、オブジェクトのデータへの保護されていない、制御されず未確認のアクセスに伴うリスクなしにパブリック データ メンバーの利便性を提供します。 これは*アクセサー*を通じて行われます。アクセサーは、基になるデータ メンバーの値を割り当てたり、取得したりする特殊なメソッドです。 [set](../../../csharp/language-reference/keywords/set.md) アクセサーはデータ メンバーの割り当てを可能にし、[get](../../../csharp/language-reference/keywords/get.md) アクセサーはデータ メンバーの値を取得します。  
  
 このサンプルでは、`Name` (string) および `Age` (int) という 2 つのプロパティを持つ `Person` クラスを示します。 両方のプロパティは `get` および `set` アクセサーを提供するため、読み取り/書き込みプロパティと見なされます。  
  
## <a name="example"></a>例  
 [!code-csharp[csProgGuideObjects#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#33)]  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 前述の例では、`Name` および `Age` プロパティは[パブリック](../../../csharp/language-reference/keywords/public.md)であり、`get` および `set` アクセサーの両方が含まれます。 そのため、任意のオブジェクトがこれらのプロパティを読み書きできます。 ただし、アクセサーのいずれかを除外することが望ましい場合もあります。 たとえば、次のように `set` アクセサーを省略すると、プロパティが読み取り専用になります。  
  
 [!code-csharp[csProgGuideObjects#87](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#87)]  
  
 また、一方のアクセサーをパブリックに公開し、もう一方を private または protected にすることもできます。 詳細については、「[アクセサーのアクセシビリティの制限 (C# プログラミング ガイド)](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)」を参照してください。  
  
 プロパティを宣言すると、プロパティをクラスのフィールドのように使用できます。 そのため、プロパティ値の取得と設定の両方で、次のように自然な構文を使用できます。  
  
 [!code-csharp[csProgGuideObjects#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#35)]  
  
 プロパティの `set` メソッドでは、特殊な `value` 変数を使用できることに注意してください。 この変数には、ユーザーが指定した値が含まれます。たとえば、次のように指定します。  
  
 [!code-csharp[csProgGuideObjects#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#36)]  
  
 `Person` オブジェクトの `Age` プロパティの値を増分する場合は、次のような簡潔な構文を使用します。  
  
 [!code-csharp[csProgGuideObjects#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#37)]  
  
 `set` メソッドと `get` メソッドがそれぞれ使用されてプロパティがモデル化されている場合、上記と同じ内容のコードは次のようになります。  
  
```csharp  
person.SetAge(person.GetAge() + 1);   
```  
  
 この例では、`ToString` メソッドが次のようにオーバーライドされます。  
  
 [!code-csharp[csProgGuideObjects#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#38)]  
  
 プログラムでは `ToString` が明示的に使用されないことに注意してください。 既定では、`WriteLine` 呼び出しによって呼び出されます。  
  
## <a name="see-also"></a>関連項目

- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)
- [プロパティ](../../../csharp/programming-guide/classes-and-structs/properties.md)
- [クラスと構造体](../../../csharp/programming-guide/classes-and-structs/index.md)
