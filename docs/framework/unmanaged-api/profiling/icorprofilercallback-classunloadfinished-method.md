---
title: ICorProfilerCallback::ClassUnloadFinished メソッド
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6330267c580901c62a74bf6d8ee8716c4fd3b1cb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468144"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a>ICorProfilerCallback::ClassUnloadFinished メソッド
クラスのアンロードが完了したことをプロファイラーに通知します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a>パラメーター  
 `classId`  
 [in]アンロードされたクラスを識別します。  
  
 `hrStatus`  
 [in]かどうか、クラスがアンロードされた正常を示す HRESULT。  
  
## <a name="remarks"></a>Remarks  
 クラスのアンロードの一部が後に続ける可能性があります、`ClassUnloadFinished`コールバック。 エラーの HRESULT で`hrStatus`失敗を示します。 ただし、成功 HRESULT で`hrStatus`のみに、クラスのアンロードの最初の部分が成功したことを示します。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorProf.idl、CorProf.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICorProfilerCallback インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ClassUnloadStarted メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)
