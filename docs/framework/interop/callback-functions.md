---
title: コールバック関数
ms.date: 03/30/2017
helpviewer_keywords:
- callback function
- platform invoke, calling unmanaged functions
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66df62262d40b4102b9dbd55969e67b6e8041480
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703069"
---
# <a name="callback-functions"></a>コールバック関数
コールバック関数は、アンマネージド DLL 関数がタスクを完了できるように支援するマネージド アプリケーション内のコードです。 コールバック関数の呼び出しは、マネージド アプリケーションから、DLL 関数を介して、マネージド実装へと間接的に渡されます。 多数ある DLL 関数の一部はプラットフォーム呼び出しと呼ばれ、正常に実行されるには、マネージド コード内にコールバック関数が必要です。  
  
 ほとんどの DLL 関数は、マネージド コードから呼び出す場合、関数のマネージド定義を作成してから、それを呼び出します。 このプロセスは簡単です。  
  
 コールバック関数を必要とする DLL 関数を使用する場合は、追加の手順がいくつかあります。 まず、関数のドキュメントを参照して、その関数にコールバックが必要かどうかを判断する必要があります。 次に、マネージド アプリケーションにコールバック関数を作成する必要があります。 最後に、DLL 関数を呼び出し、引数としてコールバック関数のポインターを渡します。 次の図は、この手順をまとめたものです。  
  
 ![プラットフォーム呼び出しコールバック](../../../docs/framework/interop/media/pinvokecallback.gif "pinvokecallback")  
コールバック関数と実装  
  
 コールバック関数は、タスクが繰り返し実行される状況での使用に最適です。 また、一般的な用途として、Win32 API の **EnumFontFamilies**、**EnumPrinters**、**EnumWindows** などの列挙関数があります。 **EnumWindows** 関数は、各ウィンドウでタスクを実行するコールバック関数を呼び出して、コンピューター上のすべての既存のウィンドウを列挙します。 手順と例については、「[方法:コールバック関数を実装する](../../../docs/framework/interop/how-to-implement-callback-functions.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目
- [方法: コールバック関数を実装する](../../../docs/framework/interop/how-to-implement-callback-functions.md)
- [DLL 関数の呼び出し](../../../docs/framework/interop/calling-a-dll-function.md)
