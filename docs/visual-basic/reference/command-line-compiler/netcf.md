---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: 987a948d739f6b9e8e5a3e8fc6eadbfd60003723
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "57203059"
---
# <a name="-netcf"></a>-netcf

  [!INCLUDE[Compact](~/includes/compact-md.md)] が対象になるようにコンパイラを設定します。  
  
## <a name="syntax"></a>構文  
  
```  
-netcf  
```  
  
## <a name="remarks"></a>Remarks  
 `-netcf`オプションは、ターゲットに Visual Basic コンパイラ、[!INCLUDE[Compact](~/includes/compact-md.md)]完全ではなく[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]します。 言語機能は、完全にのみ存在する[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]は無効です。  
  
 `-netcf`オプションがと共に使用するように設計[-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)します。 無効になっている言語機能`-netcf`同じ言語機能を対象となるファイルに存在しない`-sdkpath`します。  
  
> [!NOTE]
>  `-netcf`オプションは、Visual Studio 開発環境内からは使用できません。 コマンドラインからコンパイルする場合にのみ使用可能なです。 `-netcf` Visual Basic プロジェクトのデバイスが読み込まれるときにオプションを設定します。  
  
 `-netcf`オプションは、次の言語機能を変更します。  
  
-   [エンド\<キーワード > ステートメント](../../../visual-basic/language-reference/statements/end-keyword-statement.md)キーワードで、プログラムの実行を終了するが無効になっています。 次のプログラムをコンパイルして実行なし`-netcf`がコンパイル時にでは失敗`-netcf`します。  
  
     [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]  
  
-   遅延バインディングするには、すべての形式が無効です。 認識される遅延バインディング シナリオが発生した場合に、コンパイル時エラーが生成されます。 次のプログラムをコンパイルして実行なし`-netcf`がコンパイル時にでは失敗`-netcf`します。  
  
     [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]  
  
-   [自動](../../../visual-basic/language-reference/modifiers/auto.md)、 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)、および[Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)修飾子が無効になっています。 構文、 [Declare ステートメント](../../../visual-basic/language-reference/statements/declare-statement.md)ステートメントが変更にも`Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`します。 次のコードは、の効果を示しています。 `-netcf` 、コンパイル時にします。  
  
     [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]  
  
-   Visual Basic から削除された Visual Basic 6.0 のキーワードを使用して、別のエラーを生成時に`-netcf`使用されます。 これには、次のキーワードのエラー メッセージに影響します。  
  
    -   `Open`  
  
    -   `Close`  
  
    -   `Put`  
  
    -   `Print`  
  
    -   `Write`  
  
    -   `Input`  
  
    -   `Lock`  
  
    -   `Unlock`  
  
    -   `Seek`  
  
    -   `Width`  
  
    -   `Name`  
  
    -   `FreeFile`  
  
    -   `EOF`  
  
    -   `Loc`  
  
    -   `LOF`  
  
    -   `Line`  
  
## <a name="example"></a>例  
 次のコードのコンパイル`Myfile.vb`で、[!INCLUDE[Compact](~/includes/compact-md.md)]の既定のインストール ディレクトリにある mscorlib.dll および Microsoft.VisualBasic.dll のバージョンを使用して、 [!INCLUDE[Compact](~/includes/compact-md.md)] C ドライブにします。 通常の最新バージョンを使用すると、[!INCLUDE[Compact](~/includes/compact-md.md)]します。  
  
```console  
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>関連項目
- [Visual Basic のコマンド ライン コンパイラ](../../../visual-basic/reference/command-line-compiler/index.md)
- [コンパイル コマンド ラインのサンプル](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
