---
title: ICorDebugDataTarget2::CreateVirtualUnwinder メソッド
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 387dc484b3ada63d62ddc27318e735dfc4ea93b6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492271"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a>ICorDebugDataTarget2::CreateVirtualUnwinder メソッド
初期コンテキストからアンワインドを開始する新しいスタック アンワインダーを作成します (これは、必ずしもスレッドのリーフではありません)。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a>パラメーター  
 nativeThreadID  
 [入力] スタックをアンワインドするスレッドのネイティブ スレッド ID。  
  
 contextFlags  
 [入力] コンテキストのどの部分が `initialContext` で定義されるかを指定するフラグ。  
  
 cbContext  
 [入力] `initialContext` のサイズ。  
  
 initialContext  
 [入力] コンテキストのデータ。  
  
 ppUnwinder  
 [出力] ICorDebugVirtualUnwinder インターフェイス オブジェクトのアドレスへのポインター。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は、`S_OK`。 それ以外の `HRESULT` は失敗を示します。 失敗した`HRESULT`mscordbi によって受信は致命的と見なされ、により[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)メソッドを返す`CORDBG_E_DATA_TARGET_ERROR`します。  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
>  このメソッドは .NET ネイティブでのみ使用できます。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICorDebugDataTarget2 インターフェイス](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [デバッグ インターフェイス](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
