---
title: ICorDebugILCode2::GetLocalVarSigToken メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ee067faddf7300512387c26ae4ce4fda2b73353
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475802"
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a>ICorDebugILCode2::GetLocalVarSigToken メソッド
[.NET Framework 4.5.2 以降のバージョンでのみでサポート]  
  
 このインスタンスで示される関数について、ローカル変数のシグネチャのメタデータ トークンを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a>パラメーター  
 `pmdSig`  
 [out] この機能のローカル変数シグネチャの `mdSignature` トークンへのポインター、またはシグネチャがない場合 (つまり、機能にローカル変数がない場合) は `mdSignatureNil`。  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICorDebugILCode2 インターフェイス](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)
- [デバッグ インターフェイス](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
