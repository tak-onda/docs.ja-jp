---
title: ICorProfilerCallback::RemotingServerSendingReply メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerSendingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerSendingReply
helpviewer_keywords:
- RemotingServerSendingReply method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerSendingReply method [.NET Framework profiling]
ms.assetid: dfe84a19-2e03-4be2-8b25-f02bad38e4a9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 655b2af2efcaba82af46e92ae94abf3a4adc349c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500409"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a>ICorProfilerCallback::RemotingServerSendingReply メソッド
プロセスがリモート メソッド呼び出し要求の処理が完了して、チャネルを介して応答を送信しようとしていますが、プロファイラーに通知します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a>パラメーター  
 `pCookie`  
 [in]指定された値と対応する GUID へのポインター [icorprofilercallback::remotingclientreceivingreply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)これらの条件下で。  
  
-   リモート処理の GUID の cookie はアクティブです。  
  
-   チャネルは、メッセージの送信に成功します。  
  
-   GUID の cookie は、クライアント側のプロセスでアクティブにします。  
  
 これにより、リモート処理呼び出しと論理呼び出し履歴の作成のペアを容易にします。  
  
 `fIsAsync`  
 [in]値が`true`呼び出しが非同期。 それ以外の場合`false`します。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorProf.idl、CorProf.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICorProfilerCallback インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
