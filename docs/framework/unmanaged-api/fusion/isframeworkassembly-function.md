---
title: IsFrameworkAssembly 関数
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0fb4c98ff2c8b071f05b42aefed61485001e97f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480326"
---
# <a name="isframeworkassembly-function"></a>IsFrameworkAssembly 関数
指定したアセンブリが管理されているかどうかを示す値を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a>パラメーター  
 `pwzAssemblyReference`  
 [in]チェック対象のアセンブリの名前。  
  
 `pbIsFrameworkAssembly`  
 [out]アセンブリが管理されているかどうかを示すブール値。  
  
 `pwzFrameworkAssemblyIdentity`  
 [in]アセンブリの一意の id を含む uncanonicalized 文字列。  
  
 `pccSize`  
 [入力] `pwzFrameworkAssemblyIdentity` のサイズ。  
  
## <a name="remarks"></a>Remarks  
 `pwzAssemblyReference`パラメーターは、アセンブリの名前を含む文字列へのポインターです。  
  
 このアセンブリが、.NET Framework の一部である場合、`pbIsFrameworkAssembly`パラメーターはブール値を含む`true`します。  
  
 名前付きのアセンブリ、.NET Framework の一部でない場合、または場合、`pwzAssemblyReference`パラメーターは、アセンブリを指定していない`pbIsFrameworkAssembly`のブール値を含む`false`します。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
  
## <a name="see-also"></a>関連項目
- [Fusion グローバル静的関数](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
