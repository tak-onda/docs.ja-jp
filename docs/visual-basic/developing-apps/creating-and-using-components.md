---
title: Visual Basic でのコンポーネントの作成および使用
ms.date: 07/20/2015
helpviewer_keywords:
- components [Visual Basic]
ms.assetid: ee6a4156-73f7-4e9b-8e01-c74c4798b65c
ms.openlocfilehash: 7a0b513e5045db609550133e20c20ef65f17844c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54551920"
---
# <a name="creating-and-using-components-in-visual-basic"></a>Visual Basic でのコンポーネントの作成および使用
*コンポーネント*は、<xref:System.ComponentModel.IComponent?displayProperty=nameWithType> インターフェイスを実装するか、<xref:System.ComponentModel.IComponent> を実装するクラスから直接的または間接的に派生するクラスです。 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] のコンポーネントは、再利用可能なオブジェクトで、他のオブジェクトとやり取りでき、外部リソースの制御やデザイン時サポートが備わっています。  
  
 コンポーネントの重要な特徴の 1 つは、コンポーネントがデザイン可能であるということです。つまり、コンポーネントであるクラスは Visual Studio 統合開発環境で使用できます。 コンポーネントは、ツールボックスへの追加、フォームへのドラッグ アンド ドロップ、デザイン サーフェイスでの操作が可能です。 コンポーネントの基本のデザイン時サポートは [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] に組み込まれているため、コンポーネント開発者は追加の作業を行わずに基本のデザイン時機能を利用できます。  
  
 デザイン可能という点では、"*コントロール*" もコンポーネントに似ています。 ただし、コントロールにはユーザー インターフェイスが用意されているのに対し、コンポーネントには用意されていません。 コントロールは基本コントロール クラスである <xref:System.Windows.Forms.Control> または <xref:System.Web.UI.Control> から派生する必要があります。  
  
## <a name="when-to-create-a-component"></a>コンポーネントを作成する状況  
 デザイン サーフェイス (Windows フォーム デザイナーや Web フォーム デザイナーなど) で使用するクラスにユーザー インターフェイスがない場合、そのクラスは、コンポーネントにして、<xref:System.ComponentModel.IComponent> を実装するか、<xref:System.ComponentModel.IComponent> を直接または間接的に実装するクラスから派生させる必要があります。  
  
 <xref:System.ComponentModel.Component> クラスと <xref:System.ComponentModel.MarshalByValueComponent> クラスは、<xref:System.ComponentModel.IComponent> インターフェイスの基本実装です。 これらのクラスの主な違いは、<xref:System.ComponentModel.Component> クラスは参照渡しでマーシャリングされ、<xref:System.ComponentModel.IComponent> は値渡しでマーシャリングされることにあります。 実装のためのガイドラインを次に示します。  
  
-   コンポーネントを参照渡しでマーシャリングする必要がある場合は、<xref:System.ComponentModel.Component> から派生させます。  
  
-   コンポーネントを値渡しでマーシャリングする必要がある場合は、<xref:System.ComponentModel.MarshalByValueComponent> から派生させます。  
  
-   単一継承が原因でいずれかの基本実装からコンポーネントを派生できない場合は、<xref:System.ComponentModel.IComponent> を実装します。  
  
## <a name="component-classes"></a>コンポーネントのクラス  
 <xref:System.ComponentModel> 名前空間は、コンポーネントとコントロールの実行時およびデザイン時の動作を実装するために使用できるクラスを提供します。 この名前空間には、属性と型コンバーターの実装、データ ソースへのバインド、コンポーネントのライセンス処理のための基底クラスと基底インターフェイスが含まれています。  
  
 核となるコンポーネント クラスは次のとおりです。  
  
-   <xref:System.ComponentModel.Component>。 <xref:System.ComponentModel.IComponent> インターフェイスの基本実装。 このクラスにより、アプリケーション間でオブジェクトの共有が可能になります。  
  
-   <xref:System.ComponentModel.MarshalByValueComponent>。 <xref:System.ComponentModel.IComponent> インターフェイスの基本実装。  
  
-   <xref:System.ComponentModel.Container>。 <xref:System.ComponentModel.IContainer> インターフェイスの基本実装。 このクラスは、0 個以上のコンポーネントをカプセル化します。  
  
 コンポーネントのライセンス処理に使用するクラスのいくつかを次に示します。  
  
-   <xref:System.ComponentModel.License>。 すべてのライセンスの抽象基底クラスです。 ライセンスは、コンポーネントの特定のインスタンスに付与されます。  
  
-   <xref:System.ComponentModel.LicenseManager>。 コンポーネントにライセンスを追加し、<xref:System.ComponentModel.LicenseProvider> を管理するためのプロパティとメソッドを提供します。  
  
-   <xref:System.ComponentModel.LicenseProvider>。 ライセンス プロバイダーを実装するための抽象基底クラスです。  
  
-   <xref:System.ComponentModel.LicenseProviderAttribute>。 クラスで使用する <xref:System.ComponentModel.LicenseProvider> クラスを指定します。  
  
 コンポーネントの説明や永続化に一般的に使用するクラスを次に示します。  
  
-   <xref:System.ComponentModel.TypeDescriptor>。 属性、プロパティ、イベントなど、コンポーネントの特性に関する情報を提供します。  
  
-   <xref:System.ComponentModel.EventDescriptor>。 イベントに関する情報を提供します。  
  
-   <xref:System.ComponentModel.PropertyDescriptor>。 プロパティに関する情報を提供します。  
  
## <a name="related-sections"></a>関連項目  
 [コントロールとコンポーネントの作成時のトラブルシューティング](../../framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 一般的な問題に対処する方法について説明します。  
  
## <a name="see-also"></a>関連項目
- [方法: Windows フォームでデザイン時サポートのアクセス](../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)

