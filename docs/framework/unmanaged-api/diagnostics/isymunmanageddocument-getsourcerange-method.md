---
title: ISymUnmanagedDocument::GetSourceRange メソッド
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 767508e51660a161a7a6ff0b168a46178d66be99
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474147"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a>ISymUnmanagedDocument::GetSourceRange メソッド
指定されたバッファーに埋め込みのソースの指定した範囲を返します。 バッファーは、ソースを保持するために十分な大きさである必要があります。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
## <a name="parameters"></a>パラメーター  
 `startLine`  
 [in]現在のドキュメント内の開始行。  
  
 `startColumn`  
 [in]現在のドキュメント内の開始列。  
  
 `endLine`  
 [in]現在のドキュメントの最後の行。  
  
 `endColumn`  
 [in]現在のドキュメントの最後の列。  
  
 `cSourceBytes`  
 [in] \(バイト単位)、ソースのサイズ。  
  
 `pcSourceBytes`  
 [out]ソースのサイズを受け取る変数へのポインター。  
  
 `source`  
 [out]サイズと指定されたバイト数で、ソース ドキュメントの範囲の長さ。  
  
## <a name="return-value"></a>戻り値  
 メソッドが成功した場合は s_ok を返します。  
  
## <a name="see-also"></a>関連項目
- [ISymUnmanagedDocument インターフェイス](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
