---
title: ICorProfilerFunctionEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum
helpviewer_keywords:
- ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0a1d4a38-cd0b-4231-91df-13646218ae72
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: df3baf21de7a1e6ec0590d85719eaa40d5da489f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511905"
---
# <a name="icorprofilerfunctionenum-interface"></a>ICorProfilerFunctionEnum インターフェイス
共通言語ランタイムの関数のコレクションを順番に反復処理するメソッドを提供します。  
  
## <a name="methods"></a>メソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[Clone メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-clone-method.md)|この `ICorProfilerFunctionEnum` インターフェイスのコピーに対するインターフェイス ポインターを取得します。|  
|[GetCount メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-getcount-method.md)|アプリケーションによって読み込まれたか、またはプロファイラーによって強制的に読み込まれた関数の数を取得します。|  
|[Next メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-next-method.md)|関数のシーケンシャル コレクションから、列挙子の現在の位置以降にある、指定した数の隣接する関数を取得します。|  
|[Reset メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-reset-method.md)|列挙子のカーソルをシーケンスの開始位置に移動します。|  
|[Skip メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-skip-method.md)|指定した数の要素がスキップされるように、この列挙子のカーソルを現在の位置から進めます。|  
  
## <a name="remarks"></a>Remarks  
 `ICorProfilerFunctionEnum` インターフェイスは列挙子です。 このインターフェイスにより、配列の受信側は、受信側に適した速度で送信側から要素をプルできます。 つまり、受信側は配列要素のフローを明示的に制御できるため、大きな配列をメソッド パラメーターとして渡す場合に関連する問題を回避できます。  
  
 `ICorProfilerFunctionEnum` は、既に JIT コンパイルされた関数を列挙しますが、この中に Ngen.exe で生成されたネイティブ イメージから読み込まれた関数は含まれません。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorProf.idl、CorProf.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>関連項目
- [ICorProfilerInfo インターフェイス](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [プロファイリングのインターフェイス](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [EnumJITedFunctions メソッド](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
