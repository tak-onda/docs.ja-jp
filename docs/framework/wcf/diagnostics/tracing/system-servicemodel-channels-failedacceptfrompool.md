---
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.date: 03/30/2017
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
ms.openlocfilehash: 093a76a0157948520c2f0d8bf6145b6f78966906
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695466"
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a>System.ServiceModel.Channels.FailedAcceptFromPool
プールされた接続を再使用できませんでした。 指定されたタイムアウト期間内に再試行します。  
  
## <a name="description"></a>説明  
 この情報トレースは、プールされた接続の再使用を試みている間にエラーが発生したことを示しています。 これは、プールされた接続に互換性がない、接続の準備ができていない、または接続がアクティブなままであるために発生します。 所定のタイムアウト期間内に、他のプールされた接続を再使用する試みがさらに行われ、使用可能な接続が見つからない場合には、新しい接続が作成されます。  
  
## <a name="see-also"></a>関連項目
- [トレース](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [トレースを使用したアプリケーションのトラブルシューティング](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [管理と診断](../../../../../docs/framework/wcf/diagnostics/index.md)
