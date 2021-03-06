---
title: '方法: Windows フォーム DataGridView コントロールの列の並べ替えを有効にします。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], reordering columns
- columns [Windows Forms], reordering
ms.assetid: cc20eae3-e4db-493f-95ce-a4215e29472a
ms.openlocfilehash: 3aff0b0262441fb6c9d24240b1fe1c24707f94b8
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584253"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control"></a>方法: Windows フォーム DataGridView コントロールの列の並べ替えを有効にします。

  <xref:System.Windows.Forms.DataGridView> コントロールで列の並べ替えを有効にすると、ユーザーは列ヘッダーをマウスでドラッグすることにより列を新しい場所に移動できます。 <xref:System.Windows.Forms.DataGridView> コントロールでは、<xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> プロパティ値によってユーザーが列を別の場所に移動できるかどうかが決まります。  
  
 Visual Studio では、このタスクに対するサポートが用意されています。  参照してください[方法。フォームの DataGridView コントロールのデザイナーを使用して、Windows で有効にする列の並べ替え](enable-column-reordering-in-the-datagrid-using-the-designer.md)します。  
  
### <a name="to-enable-column-reordering-programmatically"></a>プログラムで列の並べ替えを有効にするには  
  
-   <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> プロパティを `true`に設定します。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#060)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#060)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
-   `dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。  
  
-   
  <xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。  
  
## <a name="see-also"></a>関連項目
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
- [方法: Windows フォーム DataGridView コントロールで列を固定します。](../../../../docs/framework/winforms/controls/how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)
