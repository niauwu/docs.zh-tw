---
title: ConditionedActivityGroup
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f76ef924-34ce-48ae-8c8d-48faf9697754
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7049f0ab787264893f334b8fe6aa0036e240a73f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="conditioned-activity-group"></a>ConditionedActivityGroup
本範例會示範旅遊預約應用程式。 <xref:System.Workflow.Activities.ConditionedActivityGroup> (CAG) 具有兩個程式碼活動：Car 活動與 Airline 活動。 在 `SimpleCAGWorkflow` 建構函式 (Constructor) 中，"travelNeedType" ArrayList 物件中會填入 (Populate) 所需的旅遊預約類型。 藉由將一個或兩個 `travelNeeds.Add` 陳述式標記為註解，您便可以修改 CAG 行為。 Car 與 Airline 活動兩者都有已填入 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> 的 <xref:System.Workflow.Activities.CodeCondition> 條件。 Car 活動只會在 `travelNeeds` 集合具有 `TravelNeeds.Car` 項目時執行。Airline 活動則只會在 `travelNeeds` 集合具有 `TravelNeeds.Airline` 項目時執行。  
  
 每個活動的執行都會從集合中移除對應的項目。 預設的 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A> 條件會指定當沒有子系執行或是準備執行時 (根據其 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> 條件)，CAG 便應該結束。 這表示在此範例中，當 `travelNeeds` 為空集合時，CAG 便會結束。  
  
### <a name="to-build-the-sample"></a>若要建置範例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中開啟方案。  
  
2.  按 CTRL+SHIFT+B 建置此方案。  
  
3.  按 CTRL+F5 執行方案，但不進行偵錯。  
  
### <a name="to-run-the-sample"></a>若要執行範例  
  
-   在 [SDK 命令提示字元] 視窗中，於 SimpleCAG\bin\debug 資料夾 (若是 Visual Basic 版本的範例，則是 SimpleCAG\bin 資料夾) 中執行此 .exe 檔案，該資料夾位於此範例的主要資料夾下方。  
  
> [!IMPORTANT]
>  這些範例可能已安裝在您的電腦上。 請先檢查下列 (預設) 目錄，然後再繼續：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目錄不存在，請移至 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4  (適用於 .NET Framework 4 的 Windows Communication Foundation (WCF) 與 Windows Workflow Foundation (WF) 範例)](http://go.microsoft.com/fwlink/?LinkId=150780) ，以下載所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 範例。 此範例位於下列目錄：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\SimpleCAG`  
  
## <a name="see-also"></a>請參閱  
 <xref:System.Workflow.Activities.ConditionedActivityGroup>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>  
 <xref:System.Workflow.Activities.CodeCondition>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A>
