---
title: "路由合約 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9ceea7ae-ea19-4cf9-ba4f-d071e236546d
caps.latest.revision: 7
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 7
---
# 路由合約
路由合約會定義路由服務可以處理的訊息模式。每一個合約都是無型別合約，可讓服務在不知道訊息結構描述或動作的情況下接收訊息。如此可讓路由服務以一般方式路由傳送訊息，而不需要額外設定所路由傳送之基礎訊息的細節。  
  
## 路由合約  
 由於路由服務接受泛型 WCF 訊息物件，因此選取合約時最重要的考量會是通道的組織結構，此通道將在與用戶端和服務進行通訊時使用。處理訊息時，路由服務會使用對稱的訊息幫浦，因此一般來說，傳入合約的組織結構必須符合傳出合約的組織結構。不過，在某些情況下服務模型的發送器可以修改組織結構，例如，當發送器傳送雙工通道至要求\-回覆通道時，或是在不需要且未使用工作階段支援時從通道中移除 \(也就是當 **SessionMode.Allowed** 時，將 **IInputSessionChannel** 轉換為 **IInputChannel**\)。  
  
 為了支援這些訊息幫浦，路由服務會在 <xref:System.ServiceModel.Routing> 命名空間中提供合約，這些合約必須在定義路由服務使用的服務端點時使用。這些都是無型別合約，允許接收任何訊息型別或動作，並且可讓路由服務在不知道特定訊息結構描述的情況下處理訊息。如需路由服務所使用合約的詳細資訊，請參閱[Routing Contracts](../../../../docs/framework/wcf/feature-details/routing-contracts.md)。  
  
 路由服務提供的合約位於 <xref:System.ServiceModel.Routing> 命名空間中，並且將於下表中說明。  
  
|合約|形狀|通道類型|  
|--------|--------|----------|  
|<xref:System.ServiceModel.Routing.ISimplexDatagramRouter>|SessionMode \= SessionMode.Allowed<br /><br /> AsyncPattern \= true<br /><br /> IsOneWay \= true|IInputChannel \-\> IOutputChannel|  
|<xref:System.ServiceModel.Routing.ISimplexSessionRouter>|SessionMode \= SessionMode.Required<br /><br /> AsyncPattern \= true<br /><br /> IsOneWay \= true|IInputSessionChannel \-\> IOutputSessionChannel|  
|<xref:System.ServiceModel.Routing.IRequestReplyRouter>|SessionMode \= SessionMode.Allowed<br /><br /> AsyncPattern \= true|IReplyChannel \-\> IRequestChannel|  
|<xref:System.ServiceModel.Routing.IDuplexSessionRouter>|SessionMode\=SessionMode.Required<br /><br /> CallbackContract\=typeof\(ISimplexSession\)<br /><br /> AsyncPattern \= true<br /><br /> IsOneWay \= true<br /><br /> TransactionFlow\(TransactionFlowOption.Allowed\)|IDuplexSessionChannel \-\> IDuplexSessionChannel|  
  
## 請參閱  
 [Routing Service](http://msdn.microsoft.com/zh-tw/5ac8718c-bcef-456f-bfd5-1e60a30d6eaa)   
 [路由簡介](../../../../docs/framework/wcf/feature-details/routing-introduction.md)