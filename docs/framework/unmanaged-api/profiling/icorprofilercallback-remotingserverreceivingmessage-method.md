---
title: ICorProfilerCallback::RemotingServerReceivingMessage メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerReceivingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 952ae17fa288abe6b97f1d8630da2c8f320f955b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476282"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a>ICorProfilerCallback::RemotingServerReceivingMessage メソッド
プロセスがリモート メソッド呼び出しまたはアクティブ化要求を受信したことをプロファイラーに通知します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a>パラメーター  
 `pCookie`  
 [in]指定された値に対応する値[icorprofilercallback::remotingclientsendingmessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)これらの条件下で。  
  
-   リモート処理の GUID の cookie はアクティブです。  
  
-   チャネルは、メッセージの送信に成功します。  
  
-   GUID の cookie は、クライアント側のプロセスでアクティブにします。  
  
 これにより、リモート処理呼び出しと論理呼び出し履歴の作成のペアを容易にします。  
  
 `fIsAsync`  
 [in]値が`true`呼び出しが非同期。 それ以外の場合`false`します。  
  
## <a name="remarks"></a>Remarks  
 メッセージの要求が非同期の場合は、任意のスレッドによって、要求を処理することができます。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorProf.idl、CorProf.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICorProfilerCallback インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
