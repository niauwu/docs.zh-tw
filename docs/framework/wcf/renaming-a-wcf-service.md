---
title: 重新命名 WCF 服務
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f2ab3d780f85131fc7adf24c5f420bd5fe643d9e
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2018
---
# <a name="renaming-a-wcf-service"></a>重新命名 WCF 服務
本主題說明如何重新命名 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 服務。  
  
## <a name="renaming-a-wcf-service"></a>重新命名 WCF 服務  
 請執行下列步驟，以重新命名 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 範本中的服務。  
  
-   變更實作服務的類別名稱。  
  
-   在服務的組態檔中，如下列範例所示，將服務的名稱變更為您選擇的新名稱。 視您的裝載模型而定，組態檔可能是 app.config 或 web.config 檔案。  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
-   如果您的服務是 Webhosted，則服務會使用 *.svc 檔案。 如下列範例所示，開啟 svc 檔案並修改您的服務名稱。 對於自我裝載應用程式，則不需要執行這個步驟，因為沒有 svc 檔案。  
  
```  
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a>重新命名 WCF 服務合約  
  
-   請執行下列步驟，以重新命名服務合約。  
  
-   變更服務合約的名稱。  
  
-   在服務的組態檔中，如下列範例所示，將服務合約的名稱變更為您選擇的新名稱。 視您的裝載模型而定，組態檔可能是 app.config 或 web.config 檔案。  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
