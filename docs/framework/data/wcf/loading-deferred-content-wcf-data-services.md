---
title: "載入延後的內容 (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF Data Services, 用戶端程式庫"
  - "WCF Data Services, 延後內容"
  - "WCF Data Services, 載入資料"
ms.assetid: 32f9b588-c832-44c4-a7e0-fcce635df59a
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 載入延後的內容 (WCF Data Services)
根據預設，[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 會限制查詢傳回的資料量。  不過，您可以在需要時，從資料服務明確載入其他資料，包括相關實體、分頁回應資料以及二進位資料流。  本主題描述如何將這些延後的內容載入至應用程式。  
  
## 相關實體  
 執行查詢時，只會傳回已定址之實體集中的實體。  例如，針對 Northwind 資料服務的查詢傳回 `Customers` 實體時，即使 `Customers` 和 `Orders` 之間有關聯性，預設仍不會傳回相關的 `Orders` 實體。  另外，在資料服務中啟用分頁時，您必須從服務明確載入後續資料頁面。  有兩種方式可以載入相關實體：  
  
-   **積極式載入**：您可以使用 `$expand` 查詢選項，要求查詢傳回的實體與查詢要求之實體集的關聯性有所相關。  請在 <xref:System.Data.Services.Client.DataServiceQuery%601> 上使用 <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> 方法，將 `$expand` 選項加入至傳送給資料服務的查詢。  您可以要求多個相關的實體集，並以逗號分隔這些實體集，如下列範例所示。  查詢要求的所有實體會以單一回應傳回。  下列範例會一併傳回 `Order_Details` 和 `Customers`，以及 `Orders` 實體集：  
  
     [!code-csharp[Astoria Northwind Client#ExpandOrderDetailsSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#expandorderdetailsspecific)]
     [!code-vb[Astoria Northwind Client#ExpandOrderDetailsSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#expandorderdetailsspecific)]  
  
     [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 會使用 `$expand` 查詢選項限制為可包含在單一查詢中的 12 個實體集數目。  
  
-   **明確式載入**：您可以呼叫 <xref:System.Data.Services.Client.DataServiceContext> 執行個體上的 <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> 方法，明確載入相關實體。  每次呼叫 <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> 方法，都會對資料服務建立一個獨立的查詢。  下列範例會明確載入 `Orders` 實體的 `Order_Details`：  
  
     [!code-csharp[Astoria Northwind Client#LoadRelatedOrderDetailsSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#loadrelatedorderdetailsspecific)]
     [!code-vb[Astoria Northwind Client#LoadRelatedOrderDetailsSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#loadrelatedorderdetailsspecific)]  
  
 考慮要使用哪一種方式時，請了解，對資料服務要求的數目與單一回應所傳回的資料量之間必須有所取捨。  當您的應用程式需要相關物件，且您要避免明確擷取物件之額外要求所新增的延遲時，請使用積極式載入  不過，在有些情況下，當應用程式只需要特定相關實體執行個體的資料時，您應該考慮呼叫 <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> 方法，明確載入這些實體。  如需詳細資訊，請參閱[HOW TO：載入相關實體](../../../../docs/framework/data/wcf/how-to-load-related-entities-wcf-data-services.md)。  
  
## 分頁內容  
 在資料服務中啟用分頁時，資料服務在摘要中傳回的項目數量會受限於資料服務的配置。  分頁限制可以針對每個實體集進行個別設定。  如需詳細資訊，請參閱[設定資料服務](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)。  啟用分頁時，摘要中的最後一個項目會包含下一頁資料的連結。  這個連結是包含在 <xref:System.Data.Services.Client.DataServiceQueryContinuation%601> 物件之中。  執行 <xref:System.Data.Services.Client.DataServiceQuery%601> 時，呼叫 <xref:System.Data.Services.Client.QueryOperationResponse%601> 上的 <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A> 方法，即可取得下一頁資料的 URI。  傳回的 <xref:System.Data.Services.Client.DataServiceQueryContinuation%601> 物件就能用來載入下一頁的結果。  呼叫 <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A> 方法前，您必須列舉查詢結果。  考慮第一次列舉查詢結果時，使用 `do…while` 迴圈，然後檢查 `non-null` 下一個連結值。  <xref:System.Data.Services.Client.QueryOperationResponse%601.GetContinuation%2A> 方法傳回 `null` \(在 Visual Basic 中為 `Nothing`\) 時，原始查詢不會有其他結果頁面。  下列範例顯示 `do…while` 迴圈，該迴圈會從 Northwind 範例資料服務載入已分頁的客戶資料。  
  
 [!code-csharp[Astoria Northwind Client#LoadNextLink](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#loadnextlink)]
 [!code-vb[Astoria Northwind Client#LoadNextLink](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#loadnextlink)]  
  
 當查詢要求相關的實體與要求的實體集一併以單一回應傳回時，分頁限制可能會影響回應中內嵌包含的巢狀摘要。  例如，在 Northwind 範例資料服務中，針對 `Customers` 實體集設定分頁限制時，您也可以針對相關 `Orders` 實體集設定獨立的分頁限制，如下列定義 Northwind 範例資料服務的 Northwind.svc.cs 檔案範例所示。  
  
 [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind.svc.cs#dataserviceconfigpaging)]
 [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
 在這種狀況下，您必須為最上層 `Customers` 和巢狀 `Orders` 實體摘要兩者實作分頁。  下列範例顯示 `while` 迴圈，此迴圈用來載入與選取之 `Customers` 實體相關的 `Orders` 實體頁面。  
  
 [!code-csharp[Astoria Northwind Client#LoadNextOrdersLink](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#loadnextorderslink)]
 [!code-vb[Astoria Northwind Client#LoadNextOrdersLink](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#loadnextorderslink)]  
  
 如需詳細資訊，請參閱[HOW TO：載入分頁結果](../../../../docs/framework/data/wcf/how-to-load-paged-results-wcf-data-services.md)。  
  
## 二進位資料流  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 可讓您存取二進位大型物件 \(BLOB\) 資料，做為資料流。  資料流會延後二進位資料的載入，直到需要為止，因此用戶端可以更有效地處理這些資料。  為了利用這個功能，資料服務必須實作 <xref:System.Data.Services.Providers.IDataServiceStreamProvider> 提供者。  如需詳細資訊，請參閱[資料流處理提供者](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md)。  啟用資料流時，將會傳回沒有相關二進位資料的實體類型。  在此情況下，您必須使用 <xref:System.Data.Services.Client.DataServiceContext> 類別的 <xref:System.Data.Services.Client.DataServiceContext.GetReadStream%2A> 方法，從服務存取二進位資料的資料流。  同樣地，使用 <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> 方法，可加入或變更實體的二進位資料，作為資料流。  如需詳細資訊，請參閱[使用二進位資料](../../../../docs/framework/data/wcf/working-with-binary-data-wcf-data-services.md)。  
  
## 請參閱  
 [WCF Data Services 用戶端程式庫](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)   
 [查詢資料服務](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)