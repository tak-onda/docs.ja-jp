---
title: ICLRTaskManager::GetCurrentTaskType メソッド
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTaskType
helpviewer_keywords:
- GetCurrentTaskType method [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTaskType method [.NET Framework hosting]
ms.assetid: 6b0d9259-dbe2-45bb-b34d-990f60c73424
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f75538ff7f6c3266f44495b4170007a4802fee1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487448"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a>ICLRTaskManager::GetCurrentTaskType メソッド
現在実行しているタスクの種類を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a>パラメーター  
 `pTaskType`  
 [out]値へのポインター、 [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md)現在実行しているタスクの種類を示す列挙体。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** MSCorEE.h  
  
 **ライブラリ:** MSCorEE.dll でリソースとして含まれます  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICLRTaskManager インターフェイス](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
