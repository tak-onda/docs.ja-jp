---
title: 例外処理
description: 例外処理の基礎を習得F#例外処理の式と関数へのリンクを検索します。
ms.date: 05/16/2016
ms.openlocfilehash: 187236ca380c7de0b3714160f6c3703f8fb93d5a
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614442"
---
# <a name="exception-handling"></a>例外処理

このセクションでは、F# 言語での例外処理のサポートについて説明します。

## <a name="exception-handling-basics"></a>例外処理の基礎
例外処理は、.NET Framework においてエラー条件を処理するための標準的な方法です。 したがって、F# を含むすべての .NET 言語でこのメカニズムがサポートされている必要があります。 *例外*は、エラーに関する情報をカプセル化するオブジェクトです。 エラーが発生すると、例外が生成され、通常の実行が停止します。 代わりに、ランタイムによって適切な例外ハンドラーが検索されます。 検索は、現在の関数で開始され、一致するハンドラーが見つかるまで、呼び出し元のレイヤーのスタックを上位に向かって検索します。 見つかったハンドラーが実行されます。

また、スタックはアンワインドされているため、ランタイムによって `finally` ブロック内のコードがすべて実行されます。これにより、アンワインド プロセスでオブジェクトが適切にクリーンアップされることが保証されます。

## <a name="related-topics"></a>関連トピック

|Title|説明|
|-----|-----------|
|[例外の種類](exception-types.md)|例外の種類を宣言する方法について説明します。|
|[例外処理:`try...with`式](the-try-with-expression.md)|例外処理をサポートする言語構成要素について説明します。|
|[例外処理:`try...finally`式](the-try-finally-expression.md)|例外がスローされたときに、クリーンアップ コードをスタック アンワインドとして実行するための言語構成要素について説明します。|
|[例外: `raise` 関数](the-raise-Function.md)|例外オブジェクトをスローする方法について説明します。|
|[例外処理:`failwith`関数](the-failwith-function.md)|F# の一般的な例外を生成する方法について説明します。|
|[例外処理:`invalidArg`関数](the-invalidArg-function.md)|無効な引数の例外を生成する方法について説明します。|