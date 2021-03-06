---
title: "SystemWebRouting 整合範例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: de8869956a59cb47623dbc4d84763e19d6f181bf
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/27/2018
---
# <a name="systemwebrouting-integration-sample"></a>SystemWebRouting 整合範例
這個範例示範裝載層與 <xref:System.Web.Routing> 命名空間中的類別整合。 <xref:System.Web.Routing> 命名空間中的類別可讓應用程式使用不會直接回應實體資源的 URL。 使用 Web 路由可讓開發人員建立 HTTP 的虛擬位址，並且接著對應回實體 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服務。 當 WCF 服務必須在不需要實體檔案或資源的情況下裝載，或是服務必須使用不包含 .html 或 .aspx 等檔案的 URL 存取時，這種方式會相當實用。 這個範例將示範如何使用 <xref:System.Web.Routing.RouteTable> 類別來建立虛擬 URI，以便對應至 global.asax 中所定義的執行中服務。 

> [!NOTE]
>  <xref:System.Web.Routing> 命名空間中的類別只適用於透過 HTTP 裝載的服務。  
  
這個範例會使用 WCF 來建立兩個 RSS 摘要：`movies`摘要和`channels`摘要。 啟動服務的 Url 不包含副檔名且已登錄在`Application_Start`方法`Global`類別衍生自<xref:System.Web.HttpApplication>類別。  
  
> [!NOTE]
>  此範例僅適用於網際網路資訊服務 (IIS) 7.0 中及更新版本，與 IIS 6.0 使用不同的方法支援無副檔名 Url。  

#### <a name="to-download-this-sample"></a>若要下載這個範例
  
此範例可能已安裝在電腦上。 請先檢查下列 (預設) 目錄，然後再繼續。  
   
`<InstallDrive>:\WF_WCF_Samples`  
   
 如果此目錄不存在，請移至 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4  (適用於 .NET Framework 4 的 Windows Communication Foundation (WCF) 與 Windows Workflow Foundation (WF) 範例)](http://go.microsoft.com/fwlink/?LinkId=150780) ，以下載所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 範例。 此範例位於下列目錄。  
   
`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a>若要使用這個範例  
  
1.  使用 Visual Studio，開啟 WebRoutingIntegration.sln 檔案。  
  
2.  若要執行方案並啟動 Web 程式開發伺服器，請按下 F5。  
  
     範例的目錄清單隨即出現。 請注意，沒有副檔名 .svc 的檔案。  
  
3.  在 [網址] 列中，加入`movies`至的 URL，使其讀 http://localhost: [port] 電影，然後按 enter。  
  
     影片摘要會出現在瀏覽器中。  
  
4.  在位址列中，將 `channels` 加入至 URL 成為 http://localhost:[port]/channels，然後按 ENTER。  
  
     通道摘要會出現在瀏覽器中。  
  
5.  按 ALT+F4，關閉 Web 瀏覽器。  
  
     如果尚未結束程式開發伺服器，以滑鼠右鍵按一下通知區域圖示，然後選取**停止**。  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a>若要在 IIS 中裝載時使用這個範例  
  
1.  使用 Visual Studio，開啟 WebRoutingIntegration.sln 檔案。  
  
2.  按下 CTRL+SHIFT+B 建置此專案。  
  
3.  在 [Internet Information Services (IIS) 管理員] 中建立 Web 應用程式。  
  
    1.  在 [IIS 管理員] 中，以滑鼠右鍵按一下**Default Web Site**選取**新增應用程式**。  
  
    2.  如**別名**，輸入`WebRoutingIntegration`。  
  
    3.  如**實體路徑**，選取專案內的 [服務] 資料夾。  
  
    4.  Press **OK**.  
  
4.  啟動應用程式，以滑鼠右鍵按一下 Web 應用程式，然後選取**管理應用程式**然後**瀏覽**。  
  
5.  在位址列中，將 `movies` 加入至 URL 成為 http://localhost:[port]/movies，然後按 ENTER。  
  
     影片摘要會出現在瀏覽器中。  
  
6.  在位址列中，將 `channels` 加入至 URL 成為 http://localhost:[port]/channels，然後按 ENTER。  
  
     通道摘要會出現在瀏覽器中。  
  
7.  按 ALT+F4，關閉 Web 瀏覽器。  
  
 這個範例將示範裝載層能夠使用 <xref:System.Web.Routing> 命名空間中的類別撰寫，以便路由傳送透過 HTTP 裝載之服務的要求。  
  
> [!NOTE]
>  您必須更新的預設應用程式集區版本[!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]如果它設定為第 2 版。  
  
## <a name="see-also"></a>請參閱  
 [AppFabric 主控與持續性範例](http://go.microsoft.com/fwlink/?LinkId=193961)
