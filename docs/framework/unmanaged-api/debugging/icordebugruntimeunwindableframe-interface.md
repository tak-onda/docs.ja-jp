---
title: ICorDebugRuntimeUnwindableFrame インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f006085aba140264e2a2605adce39924dbe082e4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568115"
---
# <a name="icordebugruntimeunwindableframe-interface"></a>ICorDebugRuntimeUnwindableFrame インターフェイス
共通言語ランタイム (CLR: Common Language Runtime) でフレームをアンワインドする必要のあるアンマネージ メソッドに対してサポートを提供します。  
  
## <a name="remarks"></a>Remarks  
 `ICorDebugRuntimeUnwindableFrame` ICorDebugFrame インターフェイスの特殊化されたバージョンです。 現在のスタックのフレームをアンワインドするランタイムを必要とする非管理対象のメソッドによって使用されます。 既存のアンワインド規則は機能せず、JIT コンパイル コードを使用しないためです。 デバッガーでは、アンワインド可能のフレームを見てを使用する、 [icordebugstackwalk::next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)メソッドが、アンワインドは自体検査を実行する必要があります。 デバッガーを受信すると、 `ICorDebugRuntimeUnwindableFrame`、呼び出すことができます、 [icordebugstackwalk::getcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)フレームのコンテキストを取得します。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [デバッグ インターフェイス](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [デバッグ](../../../../docs/framework/unmanaged-api/debugging/index.md)
