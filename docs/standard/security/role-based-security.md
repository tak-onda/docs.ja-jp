---
title: ロール ベース セキュリティ
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- role-based security, about role-based security
- user authentication, principals
- principals [.NET Framework]
- security [.NET Framework], role-based
- permissions [.NET Framework], principals
- authentication [.NET Framework], principals
- role-based security, principals
ms.assetid: 578cc32b-5654-4d8b-9d8c-ebcbc5c75390
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 596165bfac9c65898448714a4477b7f045bd87d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582533"
---
# <a name="role-based-security"></a>ロール ベース セキュリティ
財務アプリケーションや業務アプリケーションでは、ポリシーを適用するためにロールが使用されることがよくあります。 たとえば、要求を出しているユーザーが指定のロールのメンバーかどうかに基づいて、処理するトランザクションのサイズにアプリケーションが制限を課すことがあります。 たとえば、事務員には指定のしきい値よりも小さいトランザクションを処理する権限が与えられ、スーパーバイザにはより高いしきい値が与えられ、その上司にはさらに高いしきい値が与えられる (または制限がまったくない)、という場合です。 アプリケーションで 1 つのアクションを完了するために複数の承認を必要とするときにも、ロール ベース セキュリティを使用できます。 たとえば、どの社員も購買の要求を生成できるものの、その要求を仕入先に送信できる購買発注に変換できるのは購買部門だけにする場合などが考えられます。  
  
 .NET Framework のロール ベース セキュリティでは、関連付けられた ID で構築されるプリンシパルについての情報を現在のスレッドで使用できるようにすることによって、承認をサポートします。 この場合の ID (および ID を利用して定義されるプリンシパル) は、Windows アカウントに基づく ID か、または Windows アカウントとは無関係のカスタム ID です。 .NET Framework アプリケーションは、プリンシパルの ID、ロール メンバーシップ、またはその両方に基づいて、承認の決定を行うことができます。 ロールとは、セキュリティに関して同じ特権を持つプリンシパルの名前付きセット (窓口係や責任者など) です。 プリンシパルは、1 つ以上のロールのメンバーであることができます。 このため、アプリケーションはロール メンバーシップを使用して、要求されたアクションを実行する権限がプリンシパルにあるかどうかを決定できます。  
  
 使いやすさ、およびコード アクセス セキュリティとの一貫性を実現するため、.NET Framework のロール ベース セキュリティには <xref:System.Security.Permissions.PrincipalPermission?displayProperty=nameWithType> オブジェクトが用意されています。共通言語ランタイムは、このオブジェクトを使用することによって、コード アクセス セキュリティ チェックに似た方法で承認を実行できます。 <xref:System.Security.Permissions.PrincipalPermission> クラスは、プリンシパルが一致している必要のある ID またはロールを表し、宣言セキュリティ チェックと強制セキュリティ チェックの両方と互換性があります。 プリンシパルの ID 情報に直接アクセスし、必要なときに、コード内でロール チェックと ID チェックを実行することもできます。  
  
 .NET Framework のロール ベース セキュリティには、幅広いアプリケーションのニーズを満たせるだけの柔軟性と拡張性があります。 COM+ 1.0 Services などの既存の認証インフラストラクチャと相互運用する方法と、カスタムの認証システムを作成する方法のどちらかを選択できます。 ロール ベース セキュリティは、主にサーバー上で処理される ASP.NET Web アプリケーションでの使用に適しています。 とはいえ、.NET Framework のロール ベース セキュリティは、クライアントとサーバーのどちらでも使用できます。  
  
 このセクションの内容を読み取る前に記載されている内容を理解することを確認してください[セキュリティの基本概念](../../../docs/standard/security/key-security-concepts.md)です。  
  
## <a name="related-topics"></a>関連トピック  
  
|タイトル|説明|  
|-----------|-----------------|  
|[プリンシパル オブジェクトと ID オブジェクト](../../../docs/standard/security/principal-and-identity-objects.md)|Windows ID と Windows プリンシパル、汎用 ID と汎用プリンシパルの両方について、セットアップと管理方法を説明します。|  
|[セキュリティの基本概念](../../../docs/standard/security/key-security-concepts.md)|.NET Framework のセキュリティを使用する前に理解しておく必要のある、基本的な概念について説明します。|  
  
## <a name="reference"></a>参照  
 <xref:System.Security.Permissions.PrincipalPermission?displayProperty=nameWithType>
