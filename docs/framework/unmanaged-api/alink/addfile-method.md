---
title: AddFile メソッド
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ec16776550765924e17de35674c5774212427e1a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498459"
---
# <a name="addfile-method"></a>AddFile メソッド
アセンブリには、ファイルを追加します。 非バインド モジュールの作成にも使用できます。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>パラメーター  
 `AssemblyID`  
 追加する対象のアセンブリの一意の ID。  
  
 `pszFilename`  
 追加するファイルの完全修飾名。  
  
 `dwFlags`  
 COM + FileDef フラグなど`ffContainsNoMetaData`と`ffWriteable`します。 `dwFlags` 渡される[DefineFile メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)します。  
  
 `pEmitter`  
 [IMetaDataEmit インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)メタデータを出力するために必要な場合に使用するインターフェイス。  
  
 `pFileToken`  
 追加されたファイルの一意の ID を格納する場所へのポインター。  
  
## <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、S_OK を返します。  
  
## <a name="requirements"></a>必要条件  
 Alink.h が必要です。  
  
## <a name="see-also"></a>関連項目
- [IALink インターフェイス](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 インターフェイス](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
