---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 62ce1bc179c7215d4988e4c6bda08025c3d3e5de
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286313"
---
# <a name="callbackdebug"></a>\<callbackDebug>
Windows Communication Foundation (WCF) コールバック オブジェクトのサービス デバッグを指定します。  
  
 \<system.ServiceModel >  
\<<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<callbackDebug>  
  
## <a name="syntax"></a>構文  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a>型  
 `Type`  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|クライアント コールバック オブジェクトが SOAP エラー内のマネージド例外情報をサービスに返すかどうかを指定する値。<br /><br /> プログラムでこの属性を `true` に設定すると、デバッグするために、クライアント コールバック オブジェクト内のマネージド例外情報がサービスに戻るフローを有効にできます。 **注意:** マネージド例外情報をクライアントに返すことは、セキュリティ リスクになり得ます。 これは、例外の詳細が、認証されていないクライアントによって使用可能な内部サービスの実装に関する情報を公開するためです。|  
  
### <a name="child-elements"></a>子要素  
 なし。  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|エンドポイントの動作を指定します。|  
  
## <a name="see-also"></a>関連項目
- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>
