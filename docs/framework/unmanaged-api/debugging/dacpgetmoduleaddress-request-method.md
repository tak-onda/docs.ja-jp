---
title: DacpGetModuleAddress::Request メソッド
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress::Request Method
helpviewer.keywords:
- DacpGetModuleAddress::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3cc3b0258381b10c27dd58bee66dbb6b2cf5b2c8
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351087"
---
# <a name="dacpgetmoduleaddressrequest-method"></a>DacpGetModuleAddress::Request メソッド

指定したランタイムの構造体から構造の作成要求を実行します。

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>構文

```
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a>パラメーター

`pDataModule`\
[in]シード データ モジュールへのポインター。

## <a name="remarks"></a>Remarks

この構造は、ランタイム内に収めるし、任意のヘッダーまたはライブラリ ファイルでは公開されません。 これを使用するには、最も簡単な方法は、実装を模倣するためには。

- 呼び出し元から取得した値を返す、`Request`メソッドを`IXCLRDataModule*`パラメーターは次のパラメーター。 `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`


## <a name="requirements"></a>必要条件

**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。  
**ヘッダー:** なし     
**ライブラリ:** なし  
**.NET Framework のバージョン:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>関連項目

- [デバッグ](index.md)
- [DacpGetModuleAddress インターフェイス](dacpgetmoduleaddress-structure.md)