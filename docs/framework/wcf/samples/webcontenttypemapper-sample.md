---
title: "WebContentTypeMapper 範例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4fe59e7-44d8-43c6-a1f8-40c45223adca
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 34adf191d3edbff33fe989cf036c32104a6754ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="webcontenttypemapper-sample"></a>WebContentTypeMapper 範例
這個範例會示範如何將新內容型別對應至 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 訊息本文格式。  
  
 <xref:System.ServiceModel.Description.WebHttpEndpoint> 項目會插入 Web 訊息編碼器，這個編碼器可以讓 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 在相同的端點上接收 JSON、XML 或原始二進位訊息。 此編碼器會藉由尋找要求的 HTTP 內容型別來判定訊息的本文格式。 這個範例會介紹 <xref:System.ServiceModel.Channels.WebContentTypeMapper> 類別，以允許使用者控制內容型別與本文格式之間的對應。  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 會為內容型別提供一組預設對應。 例如，`application/json` 會對應至 JSON，而 `text/xml` 會對應至 XML。 未對應至 JSON 或 XML 的任何內容型別都會對應至原始二進位格式。  
  
 在某些案例中 (例如，Push-Style API)，服務開發人員不會控制由用戶端傳回的內容型別。 例如，用戶端可能會以 `text/javascript` 方式傳回 JSON，而不是以 `application/json` 方式。 在這種情況中，服務開發人員必須提供衍生自 <xref:System.ServiceModel.Channels.WebContentTypeMapper> 的型別來正確地處理指定的內容型別，如下列範例程式碼所示。  
  
```  
public class JsonContentTypeMapper : WebContentTypeMapper  
{  
    public override WebContentFormat  
               GetMessageFormatForContentType(string contentType)  
    {  
        if (contentType == "text/javascript")  
        {  
            return WebContentFormat.Json;  
        }  
        else  
        {  
            return WebContentFormat.Default;  
        }  
    }  
}  
```  
  
 此型別必須覆寫 <xref:System.ServiceModel.Channels.WebContentTypeMapper.GetMessageFormatForContentType%28System.String%29> 方法。 此方法必須評估 `contentType` 引數，並傳回下列其中一個值：<xref:System.ServiceModel.Channels.WebContentFormat.Json>、<xref:System.ServiceModel.Channels.WebContentFormat.Xml>、<xref:System.ServiceModel.Channels.WebContentFormat.Raw> 或 <xref:System.ServiceModel.Channels.WebContentFormat.Default>。 傳回的 <xref:System.ServiceModel.Channels.WebContentFormat.Default> 會延後至預設的 Web 訊息編碼器對應。 在先前的範例程式碼中，`text/javascript` 內容型別會對應至 JSON，而所有其他對應都維持不變。  
  
 若要使用 `JsonContentTypeMapper` 類別，請在 Web.config 中使用以下內容：  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <standardEndpoint name="" contentTypeMapper="Microsoft.Samples.WebContentTypeMapper.JsonContentTypeMapper, JsonContentTypeMapper, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 若要確認使用 JsonContentTypeMapper 的需求，從以上的組態檔中移除 contentTypeMapper 屬性。 嘗試使用 `text/javascript` 傳送 JSON 內容時，無法載入用戶端頁面。  
  
### <a name="to-set-up-build-and-run-the-sample"></a>若要安裝、建置及執行範例  
  
1.  請確定您已執行[的 Windows Communication Foundation 範例的單次安裝程序](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2.  中所述，建置此方案 WebContentTypeMapperSample.sln[建置 Windows Communication Foundation 範例](../../../../docs/framework/wcf/samples/building-the-samples.md)。  
  
3.  瀏覽到 http://localhost/ServiceModelSamples/JCTMClientPage.htm (不要使用瀏覽器從專案目錄開啟 JCTMClientPage.htm)。  
  
> [!IMPORTANT]
>  這些範例可能已安裝在您的電腦上。 請先檢查下列 (預設) 目錄，然後再繼續。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目錄不存在，請移至 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4  (適用於 .NET Framework 4 的 Windows Communication Foundation (WCF) 與 Windows Workflow Foundation (WF) 範例)](http://go.microsoft.com/fwlink/?LinkId=150780) ，以下載所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 範例。 此範例位於下列目錄。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Ajax\WebContentTypeMapper`  
  
## <a name="see-also"></a>請參閱
