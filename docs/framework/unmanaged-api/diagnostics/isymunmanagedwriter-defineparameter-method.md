---
title: ISymUnmanagedWriter::DefineParameter メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineParameter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b81ee355fe375ca7a597d5f8f2fbf92f71e0bd9b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481459"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a>ISymUnmanagedWriter::DefineParameter メソッド
現在のメソッドでは、1 つのパラメーターを定義します。 パラメーターの型は、メソッドのシグネチャ内のパラメーターの位置 (シーケンス) から取得されます。  
  
 パラメーターは、特定のメソッドのメタデータで定義されているが場合、このメソッドを使用して、再定義することはありません。 シンボル リーダーは、シンボル ストアを確認する前に、パラメーターの通常のメタデータをチェックする必要があります。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a>パラメーター  
 `name`  
 [in]パラメーターの名前。  
  
 `attributes`  
 [in]パラメーターの属性。  
  
 `sequence`  
 [in]パラメーター シグネチャ。  
  
 `addrKind`  
 [in]アドレスの種類。  
  
 `addr1`  
 [in]パラメーター指定の最初のアドレス。  
  
 `addr2`  
 [in]パラメーター指定の 2 番目のアドレス。  
  
 `addr3`  
 [in]パラメーター指定の 3 番目のアドレス。  
  
## <a name="return-value"></a>戻り値  
 メソッドが成功した場合は s_ok を返します。それ以外の場合、E_FAIL またはその他のエラー コード。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>関連項目
- [ISymUnmanagedWriter インターフェイス](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
