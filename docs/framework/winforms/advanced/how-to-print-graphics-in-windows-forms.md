---
title: 如何：列印 Windows Form 中的圖形
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f9c18f563cfd1ab15740ea773effefd89206eb0a
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-print-graphics-in-windows-forms"></a>如何：列印 Windows Form 中的圖形
通常您會想要列印在 Windows 架構應用程式中的圖形。 <xref:System.Drawing.Graphics>類別提供方法來繪製至裝置，例如螢幕或印表機的物件。  
  
### <a name="to-print-graphics"></a>若要列印的圖形  
  
1.  新增<xref:System.Drawing.Printing.PrintDocument>元件加入至表單。  
  
2.  在<xref:System.Drawing.Printing.PrintDocument.PrintPage>事件處理常式，使用<xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A>屬性<xref:System.Drawing.Printing.PrintPageEventArgs>指示何種列印圖形上的印表機的類別。  
  
     下列程式碼範例顯示用來建立的藍色橢圓形的週框矩形內的事件處理常式。 矩形的位置及尺寸： 開始 100，150 250 寬度與高度為 250。  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillEllipse(Brushes.Blue, New Rectangle(100, 150, 250, 250))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Blue,   
         new Rectangle(100, 150, 250, 250));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Blue,  
             Rectangle(100, 150, 250, 250));  
       }  
    ```  
  
     (Visual C# 和[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 下列程式碼置於表單的建構函式，以註冊事件處理常式。  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Brush>  
 [Windows Forms 列印支援](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
