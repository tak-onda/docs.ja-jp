---
title: ICorDebugEval::NewObject メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97217421d30ee4065aa1b2500e9486405e438902
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471369"
---
# <a name="icordebugevalnewobject-method"></a>ICorDebugEval::NewObject メソッド
オブジェクトの新しいインスタンスの割り当てし、指定したコンス トラクター メソッドを呼び出します。  
  
 このメソッドは、.NET Framework version 2.0 で廃止されています。 使用[icordebugeval 2::newparameterizedobject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)代わりにします。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>パラメーター  
 `pConstructor`  
 [in]呼び出されるコンス トラクターです。  
  
 `nArgs`  
 [in] `ppArgs` 配列のサイズ。  
  
 `ppArgs`  
 [in]ICorDebugValue のオブジェクトのコンス トラクターに渡される引数を表す配列。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
 **ヘッダー:** CorDebug.idl、CorDebug.h  
  
 **ライブラリ:** CorGuids.lib  
  
 **.NET framework のバージョン:** 1.1, 1.0  
  
## <a name="see-also"></a>関連項目
- [NewParameterizedObject メソッド](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)
