---
title: ICLRMetaHost::ExitProcess メソッド
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eed86f37ccab2d7eefead4997362fb82d310a1d1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502377"
---
# <a name="iclrmetahostexitprocess-method"></a>ICLRMetaHost::ExitProcess メソッド
すべての読み込まれたランタイムを適切にシャット ダウンしようとしてのプロセスを終了します。 も優先されます、 [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)関数。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a>パラメーター  
 `iExitCode`  
 [in]プロセスの終了コード。  
  
## <a name="return-value"></a>戻り値  
 このメソッド、その戻り値が定義されていないためです。  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** MetaHost.h  
  
 **ライブラリ:** MSCorEE.dll でリソースとして含まれます  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICLRMetaHost インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [ホスティング](../../../../docs/framework/unmanaged-api/hosting/index.md)
