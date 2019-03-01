---
title: C# 8.0 の新機能 - C# ガイド
description: C# 8.0 で使用できる新しい機能の概要を説明します。 この記事は、プレビュー 2 での最新のものです。
ms.date: 02/12/2019
ms.openlocfilehash: 874420775215502ebdacb8420b3fe0e027d6660f
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747623"
---
# <a name="whats-new-in-c-80"></a><span data-ttu-id="5f9b3-104">C# 8.0 の新機能</span><span class="sxs-lookup"><span data-stu-id="5f9b3-104">What's new in C# 8.0</span></span>

<span data-ttu-id="5f9b3-105">C# 言語では、プレビュー 2 で既に試すことができる多くの機能強化が行われています。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-105">There are many enhancements to the C# language that you can try out already with preview 2.</span></span> <span data-ttu-id="5f9b3-106">プレビュー 2 で追加された新機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-106">The new features added in preview 2 are:</span></span>

- <span data-ttu-id="5f9b3-107">[パターン マッチングの拡張機能](#more-patterns-in-more-places):</span><span class="sxs-lookup"><span data-stu-id="5f9b3-107">[Pattern matching enhancements](#more-patterns-in-more-places):</span></span>
  * [<span data-ttu-id="5f9b3-108">switch 式</span><span class="sxs-lookup"><span data-stu-id="5f9b3-108">Switch expressions</span></span>](#switch-expressions)
  * [<span data-ttu-id="5f9b3-109">プロパティのパターン</span><span class="sxs-lookup"><span data-stu-id="5f9b3-109">Property patterns</span></span>](#property-patterns)
  * [<span data-ttu-id="5f9b3-110">タプル パターン</span><span class="sxs-lookup"><span data-stu-id="5f9b3-110">Tuple patterns</span></span>](#tuple-patterns)
  * [<span data-ttu-id="5f9b3-111">位置指定パターン</span><span class="sxs-lookup"><span data-stu-id="5f9b3-111">Positional patterns</span></span>](#positional-patterns)
- [<span data-ttu-id="5f9b3-112">using 宣言</span><span class="sxs-lookup"><span data-stu-id="5f9b3-112">Using declarations</span></span>](#using-declarations)
- [<span data-ttu-id="5f9b3-113">静的ローカル関数</span><span class="sxs-lookup"><span data-stu-id="5f9b3-113">Static local functions</span></span>](#static-local-functions)
- [<span data-ttu-id="5f9b3-114">破棄可能な ref 構造体</span><span class="sxs-lookup"><span data-stu-id="5f9b3-114">Disposable ref structs</span></span>](#disposable-ref-structs)

<span data-ttu-id="5f9b3-115">以下の言語機能は、C# 8.0 プレビュー 1 で初めて導入されたものです。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-115">The following language features first appeared in C# 8.0 preview 1:</span></span>

- [<span data-ttu-id="5f9b3-116">Null 許容参照型</span><span class="sxs-lookup"><span data-stu-id="5f9b3-116">Nullable reference types</span></span>](#nullable-reference-types)
- [<span data-ttu-id="5f9b3-117">非同期ストリーム</span><span class="sxs-lookup"><span data-stu-id="5f9b3-117">Asynchronous streams</span></span>](#asynchronous-streams)
- [<span data-ttu-id="5f9b3-118">インデックスと範囲</span><span class="sxs-lookup"><span data-stu-id="5f9b3-118">Indices and ranges</span></span>](#indices-and-ranges)

> [!NOTE]
> <span data-ttu-id="5f9b3-119">この記事の最後の更新は、C# 8.0 プレビュー 2 に関するものです。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-119">This article was last updated for C# 8.0 preview 2.</span></span>

<span data-ttu-id="5f9b3-120">この記事の以降では、これらの機能について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-120">The remainder of this article briefly describes these features.</span></span> <span data-ttu-id="5f9b3-121">詳細な記事がある場合は、それらのチュートリアルと概要へのリンクが提供されています。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-121">Where in-depth articles are available, links to those tutorials and overviews are provided.</span></span>

## <a name="more-patterns-in-more-places"></a><span data-ttu-id="5f9b3-122">より多くの場所でより多くのパターン</span><span class="sxs-lookup"><span data-stu-id="5f9b3-122">More patterns in more places</span></span>

<span data-ttu-id="5f9b3-123">**パターン マッチング**では、関連はあっても種類が異なるデータをまたがってシェイプに依存する機能を提供するツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-123">**Pattern matching** gives tools to provide shape-dependent functionality across related but different kinds of data.</span></span> <span data-ttu-id="5f9b3-124">C# 7.0 では、[`is`](../language-reference/keywords/is.md) 式と [`switch`](../language-reference/keywords/switch.md) ステートメントを使用することで、型パターンと定数パターンの構文が導入されました。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-124">C# 7.0 introduced syntax for type patterns and constant patterns by using the [`is`](../language-reference/keywords/is.md) expression and the [`switch`](../language-reference/keywords/switch.md) statement.</span></span> <span data-ttu-id="5f9b3-125">これらの機能では、データと機能が分かれて存在するプログラミング パラダイムのサポートに向けた最初の試験的なステップが示されました。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-125">These features represented the first tentative steps toward supporting programming paradigms where data and functionality live apart.</span></span> <span data-ttu-id="5f9b3-126">業界はマイクロサービスと他のクラウド ベース アーキテクチャに向けて移動しており、他の言語ツールが必要になっています。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-126">As the industry moves toward more microservices and other cloud-based architectures, other language tools are needed.</span></span>

<span data-ttu-id="5f9b3-127">C# 8.0 では、このボキャブラリが展開されて、コードのより多くの場所で、より多くのパターン式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-127">C# 8.0 expands this vocabulary so you can use more pattern expressions in more places in your code.</span></span> <span data-ttu-id="5f9b3-128">データと機能が分かれているときは、これらの機能を検討してください。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-128">Consider these features when your data and functionality are separate.</span></span> <span data-ttu-id="5f9b3-129">アルゴリズムがオブジェクトのランタイム型以外の事実に依存している場合は、パターン マッチングを検討してください。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-129">Consider pattern matching when your algorithms depend on a fact other than the runtime type of an object.</span></span> <span data-ttu-id="5f9b3-130">これらの手法では、設計を表現する別の方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-130">These techniques provide another way to express designs.</span></span>

<span data-ttu-id="5f9b3-131">新しい場所での新しいパターンだけでなく、C# 8.0 では**再帰パターン**が追加されています。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-131">In addition to new patterns in new places, C# 8.0 adds **recursive patterns**.</span></span> <span data-ttu-id="5f9b3-132">パターン式の結果は式です。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-132">The result of any pattern expression is an expression.</span></span> <span data-ttu-id="5f9b3-133">再帰パターンは、単に、別のパターン式の出力に適用されるパターン式です。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-133">A recursive pattern is simply a pattern expression applied to the output of another pattern expression.</span></span>

### <a name="switch-expressions"></a><span data-ttu-id="5f9b3-134">switch 式</span><span class="sxs-lookup"><span data-stu-id="5f9b3-134">switch expressions</span></span>

<span data-ttu-id="5f9b3-135">多くの場合、[`switch`](../language-reference/keywords/switch.md) ステートメントでは、その各 `case` ブロックで値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-135">Often, a [`switch`](../language-reference/keywords/switch.md) statement produces a value in each of its `case` blocks.</span></span> <span data-ttu-id="5f9b3-136">**switch 式**を使用すると、より簡潔な式の構文を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-136">**Switch expressions** enable you to use more concise expression syntax.</span></span> <span data-ttu-id="5f9b3-137">反復的な `case` や `break` キーワード、および中かっこの数が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-137">There are fewer repetitive `case` and `break` keywords, and fewer curly braces.</span></span>  <span data-ttu-id="5f9b3-138">たとえば、虹の色を示す次のような列挙型について考えます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-138">As an example, consider the following enum that lists the colors of the rainbow:</span></span>

```csharp
public enum Rainbow
{
    Red,
    Orange,
    Yellow,
    Blue,
    Indigo,
    Violet
}
```

<span data-ttu-id="5f9b3-139">switch 式を含む次のメソッドを使用して、`Rainbow` の値をその RGB 値に変換できます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-139">You could convert a `Rainbow` value to its RGB values using the following method containing a switch expression:</span></span>

```csharp
public static RGBColor FromRainbow(Rainbow colorBand) =>
    colorBand switch
    {
        Rainbow.Red    => new RGBColor(0xFF, 0x00, 0x00),
        Rainbow.Orange => new RGBColor(0xFF, 0x7F, 0x00),
        Rainbow.Yellow => new RGBColor(0xFF, 0xFF, 0x00),
        Rainbow.Blue   => new RGBColor(0x00, 0x00, 0xFF),
        Rainbow.Indigo => new RGBColor(0x4B, 0x00, 0x82),
        Rainbow.Violet => new RGBColor(0x94, 0x00, 0xD3),
        _              => throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand)),
    };
```

<span data-ttu-id="5f9b3-140">この構文ではいくつかの点が改良されています。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-140">There are several syntax improvements here:</span></span>

- <span data-ttu-id="5f9b3-141">変数は `switch` キーワードの前にあります。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-141">The variable comes before the `switch` keyword.</span></span> <span data-ttu-id="5f9b3-142">順序を変えることで、switch ステートメントからの switch 式の視覚的な区別が容易になります。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-142">The different order makes it visually easy to distinguish the switch expression from the switch statement.</span></span>
- <span data-ttu-id="5f9b3-143">`case` 要素と `:` 要素は、`=>` に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-143">The `case` and `:` elements are replaced with `=>`.</span></span> <span data-ttu-id="5f9b3-144">より簡潔でわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-144">It's more concise and intuitive.</span></span>
- <span data-ttu-id="5f9b3-145">`default` ケースは、`_` 破棄に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-145">The `default` case is replaced with a `_` discard.</span></span>
- <span data-ttu-id="5f9b3-146">本体は式であり、ステートメントではありません。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-146">The bodies are expressions, not statements.</span></span>

<span data-ttu-id="5f9b3-147">従来の `switch` ステートメントを使用した同等のコードと比較してください。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-147">Contrast that with the equivalent code using the classic `switch` statement:</span></span>

```csharp
public static RGBColor fromRainbowClassic(Rainbow colorBand)
{
    switch (colorBand)
    {
        case Rainbow.Red:
            return new RGBColor(0xFF, 0x00, 0x00);
        case Rainbow.Orange:
            return new RGBColor(0xFF, 0x7F, 0x00);
        case Rainbow.Yellow:
            return new RGBColor(0xFF, 0xFF, 0x00);
        case Rainbow.Blue:
            return new RGBColor(0x00, 0x00, 0xFF);
        case Rainbow.Indigo:
            return new RGBColor(0x4B, 0x00, 0x82);
        case Rainbow.Violet:
            return new RGBColor(0x94, 0x00, 0xD3);
        default:
            throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand));
    };
}
```

### <a name="property-patterns"></a><span data-ttu-id="5f9b3-148">プロパティ パターン</span><span class="sxs-lookup"><span data-stu-id="5f9b3-148">Property patterns</span></span>

<span data-ttu-id="5f9b3-149">**プロパティ パターン**を使用すると、調査対象のオブジェクトのプロパティと照合することができます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-149">The **property pattern** enables you to match on properties of the object examined.</span></span> <span data-ttu-id="5f9b3-150">購入者の住所に基づいて消費税を計算する必要がある eコマース サイトについて考えます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-150">Consider an eCommerce site that must compute sales tax based on the buyer's address.</span></span> <span data-ttu-id="5f9b3-151">そのような計算は、`Address` クラスの核心的な役割ではありません。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-151">That computation is not a core responsibility of an `Address` class.</span></span> <span data-ttu-id="5f9b3-152">時間とともに、おそらくは住所の形式の変更より頻繁に、変更されます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-152">It will change over time, likely more often than address format changes.</span></span> <span data-ttu-id="5f9b3-153">消費税の金額は、住所の `State` プロパティに依存します。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-153">The amount of sales tax depends on the `State` property of the address.</span></span> <span data-ttu-id="5f9b3-154">次のメソッドでは、プロパティ パターンを使用して、住所と価格から消費税を計算しています。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-154">The following method uses the property pattern to compute the sales tax from the address and the price:</span></span>

```csharp
public static decimal ComputeSalesTax(Address location, decimal salePrice) =>
    location switch
    {
        { State: "WA" } => salePrice * 0.06M,
        { State: "MN" } => salePrice * 0.75M,
        { State: "MI" } => salePrice * 0.05M,
        // other cases removed for brevity...
        _ => 0M
    };
    ```

Pattern matching creates a concise syntax for expressing this algorithm.

### Tuple patterns

Some algorithms depend on multiple inputs. **Tuple patterns** allow you to switch based on multiple values expressed as a [tuple](../tuples.md).  The following code shows a switch expression for the game *rock, paper, scissors*:

```csharp
public static string RockPaperScissors(string first, string second)
    => (first, second) switch
    {
        ("rock", "paper") => "rock is covered by paper. Paper wins.",
        ("rock", "scissors") => "rock breaks scissors. Rock wins.",
        ("paper", "rock") => "paper covers rock. Paper wins.",
        ("paper", "scissors") => "paper is cut by scissors. Scissors wins.",
        ("scissors", "rock") => "scissors is broken by rock. Rock wins.",
        ("scissors", "paper") => "scissors cuts paper. Scissors wins.",
        (_, _) => "tie"
    };
    ```

The messages indicate the winner. The discard case represents the three combinations for ties, or other text inputs.

### Positional patterns

Some types include a `Deconstruct` method that deconstructs its properties into discrete variables. When a `Deconstruct` method is accessible, you can use **positional patterns** to inspect properties of the object and use those properties for a pattern.  Consider the following `Point` class that includes a `Deconstruct` method to create discrete variables for `X` and `Y`:

```csharp
public class Point
{
    public int X { get; }
    public int Y { get; }

    public Point(int x, int y) => (X, Y) = (x, y);

    public void Deconstruct(out int x, out int y) =>
        (x, y) = (X, Y);
}
```

<span data-ttu-id="5f9b3-155">次のメソッドでは、**位置指定パターン**を使用して、`x` と `y` の値を抽出しています。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-155">The following method uses the **positional pattern** to extract the values of `x` and `y`.</span></span> <span data-ttu-id="5f9b3-156">その後、`when` 句を使用して、点のクワドラントを決定します。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-156">Then, it uses a `when` clause to determine the quadrant of the point:</span></span>

```csharp
static string Quadrant(Point p) => p switch
{
    (0, 0) => "origin",
    (var x, var y) when x > 0 && y > 0 => "Quadrant 1",
    (var x, var y) when x < 0 && y > 0 => "Quadrant 2",
    (var x, var y) when x < 0 && y < 0 => "Quadrant 3",
    (var x, var y) when x > 0 && y < 0 => "Quadrant 4",
    (var x, var y) => "on a border",
    _ => "unknown"
};
```

<span data-ttu-id="5f9b3-157">前の switch での破棄パターンは、`x` または `y` のどちらか一方が 0 のときに一致しますが、両方とも 0 のときには一致しません。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-157">The discard pattern in the preceding switch matches when either `x` or `y`, but not both, is 0.</span></span> <span data-ttu-id="5f9b3-158">switch 式は、値を生成するか、または例外をスローする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-158">A switch expression must either produce a value or throw an exception.</span></span> <span data-ttu-id="5f9b3-159">どのケースとも一致しない場合、switch 式は例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-159">If none of the cases match, the switch expression throws an exception.</span></span> <span data-ttu-id="5f9b3-160">可能性のあるすべてのケースが switch 式でカバーされていない場合、コンパイラで警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-160">The compiler generates a warning for you if you do not cover all possible cases in your switch expression.</span></span>

## <a name="using-declarations"></a><span data-ttu-id="5f9b3-161">using 宣言</span><span class="sxs-lookup"><span data-stu-id="5f9b3-161">using declarations</span></span>

<span data-ttu-id="5f9b3-162">**using 宣言**は、`using` キーワードが前に付いている変数宣言です。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-162">A **using declaration** is a variable declaration preceded by the `using` keyword.</span></span> <span data-ttu-id="5f9b3-163">宣言されている変数を外側のスコープの最後に破棄する必要があることを、コンパイラに伝えます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-163">It tells the compiler that the variable being declared should be disposed at the end of the enclosing scope.</span></span> <span data-ttu-id="5f9b3-164">たとえば、テキスト ファイルを書き込む次のようなコードについて考えます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-164">For example, consider the following code that writes a text file:</span></span>

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using var file = new System.IO.StreamWriter("WriteLines2.txt");
    foreach (string line in lines)
    {
        // If the line doesn't contain the word 'Second', write the line to the file.
        if (!line.Contains("Second"))
        {
            file.WriteLine(line);
        }
    }
// file is disposed here
}
```

<span data-ttu-id="5f9b3-165">上の例では、メソッドの右中かっこに達した時点で、ファイルは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-165">In the preceding example, the file is disposed when the closing brace for the method is reached.</span></span> <span data-ttu-id="5f9b3-166">そこは、`file` が宣言されているスコープの末端です。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-166">That's the end of the scope in which `file` is declared.</span></span> <span data-ttu-id="5f9b3-167">上記のコードは、従来の [using ステートメント](../language-reference/keywords/using-statement.md)を使用する次のコードと同等です。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-167">The preceding code is equivalent to the following code using the classic [using statements](../language-reference/keywords/using-statement.md) statement:</span></span>


```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using (var file = new System.IO.StreamWriter("WriteLines2.txt"))
    {
        foreach (string line in lines)
        {
            // If the line doesn't contain the word 'Second', write the line to the file.
            if (!line.Contains("Second"))
            {
                file.WriteLine(line);
            }
        }
    } // file is disposed here
}
```

<span data-ttu-id="5f9b3-168">上の例では、`using` ステートメントに関連付けられている右中かっこに達すると、ファイルは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-168">In the preceding example, the file is disposed when the closing brace associated with the `using` statement is reached.</span></span>

<span data-ttu-id="5f9b3-169">どちらの場合も、コンパイラでは `Dispose()` の呼び出しが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-169">In both cases, the compiler generates the call to `Dispose()`.</span></span> <span data-ttu-id="5f9b3-170">using ステートメント内の式を破棄できない場合、コンパイラでエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-170">The compiler generates an error if the expression in the using statement is not disposable.</span></span>

## <a name="static-local-functions"></a><span data-ttu-id="5f9b3-171">静的ローカル関数</span><span class="sxs-lookup"><span data-stu-id="5f9b3-171">Static local functions</span></span>

<span data-ttu-id="5f9b3-172">`static` 修飾子をローカル関数に追加することにより、ローカル関数で外側のスコープの変数がキャプチャ (参照) されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-172">You can now add the `static` modifier to local functions to ensure that local function doesn't capture (reference) any variables from the enclosing scope.</span></span> <span data-ttu-id="5f9b3-173">それを行うと、`CS8421` "静的ローカル関数は <variable> への参照を含むことができない" が生成されます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-173">Doing so generates `CS8421`, "A static local function can't contain a reference to <variable>."</span></span> 

<span data-ttu-id="5f9b3-174">次のコードについて考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-174">Consider the following code.</span></span> <span data-ttu-id="5f9b3-175">ローカル関数 `LocalFunction` は、外側のスコープ (`M` メソッド) で宣言されている変数 `y` にアクセスしています。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-175">The local function `LocalFunction` accesses the variable `y`, declared in the enclosing scope (the method `M`).</span></span> <span data-ttu-id="5f9b3-176">そのため、`LocalFunction` では `static` 修飾子を宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-176">Therefore, `LocalFunction` can't be declared with the `static` modifier:</span></span>

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

<span data-ttu-id="5f9b3-177">次のコードには、静的ローカル関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-177">The following code contains a static local function.</span></span> <span data-ttu-id="5f9b3-178">外側のスコープ内のどの変数にもアクセスしていないため、静的にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-178">It can be static because it doesn't access any variables in the enclosing scope:</span></span>

```csharp
int M()
{
    int y = 5;
    int x = 7;
    return Add(x, y);

    static int Add(int left, int right) => left + right;
}
```

## <a name="disposable-ref-structs"></a><span data-ttu-id="5f9b3-179">破棄可能な ref 構造体</span><span class="sxs-lookup"><span data-stu-id="5f9b3-179">Disposable ref structs</span></span>

<span data-ttu-id="5f9b3-180">`ref` 修飾子付きで宣言されている `struct` ではインターフェイスを実装できないので、<xref:System.IDisposable> を実装できません。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-180">A `struct` declared with the `ref` modifier may not implement any interfaces and so cannot implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="5f9b3-181">したがって、`ref struct` を破棄できるようにするには、アクセス可能な `void Dispose()` メソッドを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-181">Therefore, to enable a `ref struct` to be disposed, it must have an accessible `void Dispose()` method.</span></span> <span data-ttu-id="5f9b3-182">これは、`readonly ref struct` 宣言にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-182">This also applies to `readonly ref struct` declarations.</span></span>

## <a name="nullable-reference-types"></a><span data-ttu-id="5f9b3-183">null 許容参照型</span><span class="sxs-lookup"><span data-stu-id="5f9b3-183">Nullable reference types</span></span>

<span data-ttu-id="5f9b3-184">null 許容注釈コンテキスト内では、参照型のすべての変数は、**null 非許容参照型**と見なされます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-184">Inside a nullable annotation context, any variable of a reference type is considered to be a **nonnullable reference type**.</span></span> <span data-ttu-id="5f9b3-185">変数が null 許容であることを示したい場合は、型名に `?` を追加し、**null 許容参照型**として変数を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-185">If you want to indicate that a variable may be null, you must append the type name with the `?` to declare the variable as a **nullable reference type**.</span></span>

<span data-ttu-id="5f9b3-186">null 非許容参照型の場合は、コンパイラでフロー分析を使用して、ローカル変数が宣言時に null 以外の値に初期化されることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-186">For nonnullable reference types, the compiler uses flow analysis to ensure that local variables are initialized to a non-null value when declared.</span></span> <span data-ttu-id="5f9b3-187">フィールドは、構築時に初期化される必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-187">Fields must be initialized during construction.</span></span> <span data-ttu-id="5f9b3-188">変数が使用可能ないずれかのコンストラクターの呼び出しまたは初期化子によって設定されていない場合、コンパイラで警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-188">The compiler generates a warning if the variable is not set by a call to any of the available constructors or by an initializer.</span></span> <span data-ttu-id="5f9b3-189">さらに、null 非許容参照型に、null になる可能性がある値を割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-189">Furthermore, nonnullable reference types can't be assigned a value that could be null.</span></span>

<span data-ttu-id="5f9b3-190">null 許容参照型の場合は、null に割り当てられたり初期化されたりしないことは確認されません。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-190">Nullable reference types aren't checked to ensure they aren't assigned or initialized to null.</span></span> <span data-ttu-id="5f9b3-191">ただし、null 許容参照型の変数が null 非許容参照型にアクセスしたり割り当てられたりするときは、その前に、コンパイラでフロー分析を使用して、null 値のチェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-191">However, the compiler uses flow analysis to ensure that any variable of a nullable reference type is checked against null before it's accessed or assigned to a nonnullable reference type.</span></span>

<span data-ttu-id="5f9b3-192">詳しくは、「[null 許容参照型](../nullable-references.md)」の概要をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-192">You can learn more about the feature in the overview of [nullable reference types](../nullable-references.md).</span></span> <span data-ttu-id="5f9b3-193">この [null 許容参照型チュートリアル](../tutorials/nullable-reference-types.md)の新しいアプリケーションを使って、自分で試してみてください。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-193">Try it yourself in a new application in this [nullable reference types tutorial](../tutorials/nullable-reference-types.md).</span></span> <span data-ttu-id="5f9b3-194">既存のコードベースを null 許容参照型を使用するように移行する手順について詳しくは、[null 許容参照型を使用するようにアプリケーションを移行する方法についてのチュートリアル](../tutorials/upgrade-to-nullable-references.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-194">Learn about the steps to migrate an existing codebase to make use of nullable reference types in the [migrating an application to use nullable reference types tutorial](../tutorials/upgrade-to-nullable-references.md).</span></span>

## <a name="asynchronous-streams"></a><span data-ttu-id="5f9b3-195">非同期ストリーム</span><span class="sxs-lookup"><span data-stu-id="5f9b3-195">Asynchronous streams</span></span>

<span data-ttu-id="5f9b3-196">C# 8.0 以降では、ストリームを非同期的に作成して使用することができます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-196">Starting with C# 8.0, you can create and consume streams asynchronously.</span></span> <span data-ttu-id="5f9b3-197">非同期ストリームを返すメソッドには、次の 3 つの特徴があります。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-197">A method that returns an asynchronous stream has three properties:</span></span>

1. <span data-ttu-id="5f9b3-198">`async` 修飾子を使用して宣言されています。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-198">It was declared with the `async` modifier.</span></span>
1. <span data-ttu-id="5f9b3-199"><xref:System.Collections.Generic.IAsyncEnumerable%601> を返します。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-199">It returns an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span>
1. <span data-ttu-id="5f9b3-200">メソッドに、連続する要素を非同期ストリームで返すための `yield return` ステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-200">The method contains `yield return` statements to return successive elements in the asynchronous stream.</span></span>

<span data-ttu-id="5f9b3-201">非同期ストリームを使用するには、ストリームの要素を列挙するときに、`foreach` キーワードの前に `await` キーワードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-201">Consuming an asynchronous stream requires you to add the `await` keyword before the `foreach` keyword when you enumerate the elements of the stream.</span></span> <span data-ttu-id="5f9b3-202">`await` キーワードを追加するには、非同期ストリームを列挙するメソッドが、`async` 修飾子を使用して宣言されていて、`async` メソッドに対して許可される型を返すようになっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-202">Adding the `await` keyword requires the method that enumerates the asynchronous stream to be declared with the `async` modifier and to return a type allowed for an `async` method.</span></span> <span data-ttu-id="5f9b3-203">通常は、<xref:System.Threading.Tasks.Task> または <xref:System.Threading.Tasks.Task%601> を返すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-203">Typically that means returning a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="5f9b3-204"><xref:System.Threading.Tasks.ValueTask> または <xref:System.Threading.Tasks.ValueTask%601> にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-204">It can also be a <xref:System.Threading.Tasks.ValueTask> or <xref:System.Threading.Tasks.ValueTask%601>.</span></span> <span data-ttu-id="5f9b3-205">同じメソッドで非同期ストリームの使用と生成の両方を行うことができます。これは、そのメソッドが <xref:System.Collections.Generic.IAsyncEnumerable%601> を返すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-205">A method can both consume and produce an asynchronous stream, which means it would return an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span> <span data-ttu-id="5f9b3-206">次のコードでは、1 から 20 の値のシーケンスが生成され、各値の間に 100 ミリ秒の待機が設けられています。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-206">The following code generates a sequence from 1 to 20, waiting 100 ms between generating each number:</span></span>

```csharp
public static async System.Collections.Generic.IAsyncEnumerable<int> GenerateSequence()
{
    for (int i = 0; i < 20; i++)
    {
        await Task.Delay(100);
        yield return i;
    }
}
```

<span data-ttu-id="5f9b3-207">シーケンスの列挙は、`await foreach` ステートメントを使用して行います。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-207">You would enumerate the sequence using the `await foreach` statement:</span></span>

```csharp
await foreach (var number in GenerateSequence())
{
    Console.WriteLine(number);
}
```

<span data-ttu-id="5f9b3-208">[非同期ストリームの作成と使用](../tutorials/generate-consume-asynchronous-stream.md)に関するチュートリアルを使用して、自分で非同期ストリームを試すことができます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-208">You can try asynchronous streams yourself in our tutorial on [creating and consuming async streams](../tutorials/generate-consume-asynchronous-stream.md).</span></span>

## <a name="indices-and-ranges"></a><span data-ttu-id="5f9b3-209">インデックスと範囲</span><span class="sxs-lookup"><span data-stu-id="5f9b3-209">Indices and ranges</span></span>

<span data-ttu-id="5f9b3-210">範囲とインデックスでは、配列、<xref:System.Span%601>、または <xref:System.ReadOnlySpan%601> 内の部分範囲を指定するための簡潔な構文が提供されます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-210">Ranges and indices provide a succinct syntax for specifying subranges in an array, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span>

<span data-ttu-id="5f9b3-211">**末尾から**インデックスを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-211">You can specify an index **from the end**.</span></span> <span data-ttu-id="5f9b3-212">**末尾から**指定するには、`^` 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-212">You specify **from the end** using the `^` operator.</span></span> <span data-ttu-id="5f9b3-213">`array[2]` が "先頭から 2 番目" の要素を意味することには慣れているでしょう。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-213">You are familiar with `array[2]` meaning the element "2 from the start".</span></span> <span data-ttu-id="5f9b3-214">今後、`array[^2]` は "末尾から 2 番目" の要素を意味するようになります。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-214">Now, `array[^2]` means the element "2 from the end".</span></span> <span data-ttu-id="5f9b3-215">インデックス `^0` は、"末尾" つまり最後の要素の後のインデックスを意味します。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-215">The index `^0` means "the end", or the index that follows the last element.</span></span>

<span data-ttu-id="5f9b3-216">**範囲**は、**範囲演算子** `..` を使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-216">You can specify a **range** with the **range operator**: `..`.</span></span> <span data-ttu-id="5f9b3-217">たとえば、`0..^0` は配列の範囲全体を指定します。0 は先頭からですが、末尾の 0 は含まれません。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-217">For example, `0..^0` specifies the entire range of the array: 0 from the start up to, but not including 0 from the end.</span></span> <span data-ttu-id="5f9b3-218">どちらのオペランドでも、"先頭から" または "末尾から" を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-218">Either operand may use "from the start" or "from the end".</span></span> <span data-ttu-id="5f9b3-219">さらに、どちらのオペランドも省略できます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-219">Furthermore, either operand may be omitted.</span></span> <span data-ttu-id="5f9b3-220">先頭インデックスの既定値は `0`、末尾インデックスの既定値は `^0` です。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-220">The defaults are `0` for the start index, and `^0` for the end index.</span></span>

<span data-ttu-id="5f9b3-221">いくつか例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-221">Let's look at a few examples.</span></span> <span data-ttu-id="5f9b3-222">先頭および末尾からのインデックスの注釈が付けられた、次のような配列について考えます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-222">Consider the following array, annotated with its index from the start and from the end:</span></span>

```csharp
var words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};
```

<span data-ttu-id="5f9b3-223">各要素のインデックスによって "先頭から" と "末尾から" の概念が強調されており、その範囲では範囲の末尾が除外されています。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-223">The index of each element reinforces the concept of "from the start", and "from the end", and that ranges are exclusive of the end of the range.</span></span> <span data-ttu-id="5f9b3-224">配列全体の "先頭" は最初の要素です。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-224">The "start" of the entire array is the first element.</span></span> <span data-ttu-id="5f9b3-225">配列全体の "末尾" は、最後の要素の "*後*" です。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-225">The "end" of the entire array is *past* the last element.</span></span>

<span data-ttu-id="5f9b3-226">最後の単語は、`^1` というインデックスで取得することができます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-226">You can retrieve the last word with the `^1` index:</span></span>

```csharp
Console.WriteLine($"The last word is {words[^1]}");
// writes "dog"
```

<span data-ttu-id="5f9b3-227">次のコードでは、単語 "quick"、"brown"、"fox" から成る部分範囲が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-227">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="5f9b3-228">それには、`words[1]` から `words[3]` までが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-228">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="5f9b3-229">要素 `words[4]` は範囲内ではありません。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-229">The element `words[4]` is not in the range.</span></span>

```csharp
var brownFox = words[1..4];
```

<span data-ttu-id="5f9b3-230">次のコードでは、"lazy" と "dog" の部分範囲が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-230">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="5f9b3-231">それには、`words[^2]` と `words[^1]` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-231">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="5f9b3-232">末尾インデックス `words[^0]` は含まれません。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-232">The end index `words[^0]` is not included:</span></span>

```csharp
var lazyDog = words[^2..^0];
```

<span data-ttu-id="5f9b3-233">次の例では、先頭と末尾の一方または両方が開いている範囲が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-233">The following examples create ranges that are open ended for the start, end, or both:</span></span>

```csharp
var allWords = words[..]; // contains "The" through "dog".
var firstPhrase = words[..4]; // contains "The" through "fox"
var lastPhrase = words[6..]; // contains "the, "lazy" and "dog"
```

<span data-ttu-id="5f9b3-234">変数として範囲を宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-234">You can also declare ranges as variables:</span></span>

```csharp
Range phrase = 1..4;
```

<span data-ttu-id="5f9b3-235">その場合、範囲は文字 `[` と `]` の内側で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f9b3-235">The range can then be used inside the `[` and `]` characters:</span></span>

```csharp
var text = words[phrase];
```