---
title: ICorDebugNativeFrame::GetLocalRegisterValue メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterValue
helpviewer_keywords:
- GetLocalRegisterValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalRegisterValue method [.NET Framework debugging]
ms.assetid: 5ccb74f3-f891-430c-b70a-e370624edde2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e6512871bf9a5cb0219a470267d1be4ecd403b3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478363"
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a>ICorDebugNativeFrame::GetLocalRegisterValue メソッド
このネイティブ フレームに指定されたレジスタに格納されているローカル変数または引数の値を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>パラメーター  
 `reg`  
 [in]値を含むレジスタを指定する"CorDebugRegister"列挙型の値。  
  
 `cbSigBlob`  
 [in]によって参照されているバイナリ メタデータ シグネチャのサイズを指定する整数、`pvSigBlob`パラメーター。  
  
 `pvSigBlob`  
 [in]A`PCCOR_SIGNATURE`値の型のバイナリ メタデータ シグネチャを示す値。  
  
 `ppValue`  
 [out]指定されたレジスタに格納されている取得した値を表す"ICorDebugValue"オブジェクトのアドレスへのポインター。  
  
## <a name="remarks"></a>Remarks  
 `GetLocalRegisterValue`ネイティブ フレームまたはの just-in-time (JIT) で、メソッドを使用できます-フレームをコンパイルします。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>関連項目

