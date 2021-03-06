---
title: '方法: 設定し、Windows フォームの NumericUpDown コントロールで数値を返す'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- numeric values [Windows Forms], Windows Forms
- Windows Forms, numeric values
- Windows Forms controls, NumericUpDown
- NumericUpDown control [Windows Forms], setting and returning values
ms.assetid: 5bd8f8cd-4c12-49ea-9cc3-2a647d064689
ms.openlocfilehash: 4fd995e5f7694616d7b6be7aa9a2eab6611997b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688962"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a>方法: 設定し、Windows フォームの NumericUpDown コントロールで数値を返す
Windows フォームの数値<xref:System.Windows.Forms.NumericUpDown>コントロールはによって決定されます。 その<xref:System.Windows.Forms.NumericUpDown.Value%2A>プロパティ。 他のプロパティと同様に、コントロールの値の条件付きテストを記述できます。 1 回、<xref:System.Windows.Forms.NumericUpDown.Value%2A>プロパティが設定されて、それを調整するには、操作を実行するコードの記述によって直接、または呼び出すことができます、<xref:System.Windows.Forms.NumericUpDown.UpButton%2A>と<xref:System.Windows.Forms.NumericUpDown.DownButton%2A>メソッド。  
  
### <a name="to-set-the-numeric-value"></a>数値の値を設定するには  
  
1.  値を割り当てる、<xref:System.Windows.Forms.NumericUpDown.Value%2A>コードまたは、[プロパティ] ウィンドウでプロパティ。  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     - または -  
  
2.  呼び出す、<xref:System.Windows.Forms.NumericUpDown.UpButton%2A>または<xref:System.Windows.Forms.NumericUpDown.DownButton%2A>メソッドで指定した値を増減させて、<xref:System.Windows.Forms.NumericUpDown.Increment%2A>プロパティ。  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a>数値の値を返す  
  
-   アクセス、<xref:System.Windows.Forms.NumericUpDown.Value%2A>コード内のプロパティ。  
  
    ```vb  
    If NumericUpDown1.Value >= 65 Then  
       MessageBox.Show("Age is: " & NumericUpDown1.Value.ToString)  
    Else  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.")  
    End If  
    ```  
  
    ```csharp  
    if(numericUpDown1.Value >= 65)  
    {  
       MessageBox.Show("Age is: " + numericUpDown1.Value.ToString());  
    }  
    else  
    {  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
    ```cpp  
    if(numericUpDown1->Value >= 65)  
    {  
       MessageBox::Show(String::Concat("Age is: ",  
          numericUpDown1->Value.ToString()));  
    }  
    else  
    {  
       MessageBox::Show  
          ("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
## <a name="see-also"></a>関連項目
- <xref:System.Windows.Forms.NumericUpDown>
- <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>
- [NumericUpDown コントロール](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)
- [NumericUpDown コントロールの概要](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)
