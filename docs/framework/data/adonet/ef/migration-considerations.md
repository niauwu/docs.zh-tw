---
title: "移轉考量 (Entity Framework) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: c85b6fe8-cc32-4642-8f0a-dc0e5a695936
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# 移轉考量 (Entity Framework)
[!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] Entity Framework 可以為現有應用程式提供幾項優勢，  其中一項最重要的優勢，就是使用概念模型將應用程式所使用的資料結構從資料來源中的結構描述分隔。  這樣能方便您以後對儲存體模型或資料來源本身進行變更，而不必對應用程式進行補償變更。  如需使用 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 之優點的詳細資訊，請參閱 [Entity Framework 概觀](../../../../../docs/framework/data/adonet/ef/overview.md)和  [實體資料模型](../../../../../docs/framework/data/adonet/entity-data-model.md)。  
  
 若要善用 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 的優勢，您可以將現有應用程式移轉至 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。  有些工作通用於所有移轉的應用程式。  這些一般工作包括將應用程式升級為使用以 Service Pack 1 \(SP1\) 3.5 版開頭的 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]、定義模型和對應，以及設定 Entity Framework。  在將應用程式移轉至 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 的時候，有其他的適用考量。  這些考量取決於要移轉的應用程式類型以及應用程式的特定功能。  本主題所提供的資訊有助於您選擇在升級現有應用程式時要使用的最佳方式。  
  
## 一般移轉考量  
 下列考量適用於將任何應用程式移轉至 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 的情況：  
  
-   任何使用以 3.5 版 SP1 開頭之 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 的應用程式都可以移轉至 Entity Framework，只要應用程式使用之資料來源的資料提供者支援 Entity Framework 即可。  
  
-   Entity Framework 可能無法支援資料來源提供者的所有功能，即使那個提供者支援 Entity Framework 也一樣。  
  
-   針對大型或複雜應用程式，您不必一次將整個應用程式移轉至 Entity Framework，  但是資料來源變更時，還是要變更未使用 Entity Framework 的任何應用程式部分。  
  
-   Entity Framework 所使用的資料提供者連接可以與應用程式的其他部分共用，因為 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 會使用 [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] 資料提供者存取資料來源。  例如，Entity Framework 是使用 SqlClient 提供者進行存取 SQL Server 資料庫。  如需詳細資訊，請參閱 [Entity Framework 的 EntityClient 提供者](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)。  
  
## 通用移轉工作  
 移轉現有應用程式至 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 的途徑取決於應用程式的類型以及現有資料存取策略。  不過，在將現有應用程式移轉至 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 時，一律必須執行下列工作：  
  
> [!NOTE]
>  使用以 [!INCLUDE[vsOrcas](../../../../../includes/vsorcas-md.md)] 開頭的實體資料模型工具時，便會自動執行上述所有工作。  如需詳細資訊，請參閱[How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/zh-tw/dadb058a-c5d9-4c5c-8b01-28044112231d)。  
  
1.  升級應用程式。  
  
     使用舊版 [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 和 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 建立的專案必須升級為以 [!INCLUDE[vsOrcas](../../../../../includes/vsorcas-md.md)] SP1 和 3.5 版 SP1 開頭的 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]。  
  
2.  定義模型與對應  
  
     模型和對應檔案定義概念模型中的實體、資料來源中的結構 \(例如資料表、預存程序和檢視表\)，以及實體與資料來源結構間的對應。  如需詳細資訊，請參閱[How to: Manually Define the Model and Mapping Files](http://msdn.microsoft.com/zh-tw/d4fd6864-f2a1-48f0-aa32-1e318775a99a)。  
  
     儲存體模型中定義的類型必須與資料來源中物件的名稱相符。  如果現有應用程式將資料公開 \(Expose\) 為物件，您必須確保概念模型中定義的實體和屬性與這些現有資料類別和屬性的名稱相符。  如需詳細資訊，請參閱[How to: Customize Modeling and Mapping Files to Work with Custom Objects](http://msdn.microsoft.com/zh-tw/bb40c4db-0121-4e45-a167-8fb06707a708)。  
  
    > [!NOTE]
    >  Entity Data Model Designer 可以用來重新命名概念模型中的實體，使其與現有物件相符。  如需詳細資訊，請參閱 [Entity Data Model Designer](http://msdn.microsoft.com/zh-tw/4ccd7ad6-b934-4f7c-82a0-cfd2d4a95faf)。  
  
3.  定義連接字串 \(Connection String\)。  
  
     針對概念模型執行查詢時，[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 會使用特殊格式化的連接字串。  此連接字串會封裝與模型和對應檔以及資料來源連接有關的資訊。  如需詳細資訊，請參閱[HOW TO：定義連接字串](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)。  
  
4.  設定 [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 專案。  
  
     您必須將 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 組件及模型和對應檔的參考加入至 [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 專案。  您可以將這些對應檔加入至專案，以確保它們與應用程式一起部署在連接字串中所指示的位置。  如需詳細資訊，請參閱[How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/zh-tw/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)。  
  
## 適用於具有現有物件的應用程式之考量  
 從 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 4 版開始，[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 可支援「單純」\(plain old\) CLR 物件 \(POCO\)，又稱為非持續性物件。  大部分的情況下，只要稍加變更您現有的物件，它們都能與 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 搭配使用。  如需詳細資訊，請參閱[Working with POCO Entities](http://msdn.microsoft.com/zh-tw/5e0fb82a-b6d1-41a1-b37b-c12db61629d3)。您也可以將應用程式移轉至 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]，並使用 Entity Framework 工具所產生的資料類別。  如需詳細資訊，請參閱[How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/zh-tw/dadb058a-c5d9-4c5c-8b01-28044112231d)。  
  
## 適用於使用 ADO.NET 提供者的應用程式之考量  
 [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] 提供者 \(如 SqlClient\) 能讓您查詢資料來源，進而傳回表格式資料。  資料也可以載入至 [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] 資料集。  下列清單說明適用於升級使用現有 [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] 提供者的應用程式之考量：  
  
 使用資料讀取器 \(Reader\) 顯示表格式資料。  
 您可以考慮使用 EntityClient 提供者執行 [!INCLUDE[esql](../../../../../includes/esql-md.md)] 查詢，並且列舉整個傳回的 <xref:System.Data.EntityClient.EntityDataReader> 物件。  只有在應用程式使用資料讀取器顯示表格式資料，而且不需要 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 提供的功能進行將資料具體化為物件、追蹤變更和處理更新時才這麼做。您可以繼續使用對資料來源進行更新的現有資料存取程式碼，不過您可以使用從 <xref:System.Data.EntityClient.EntityConnection.StoreConnection%2A> 的 <xref:System.Data.EntityClient.EntityConnection> 屬性存取的現有連接。  如需詳細資訊，請參閱 [Entity Framework 的 EntityClient 提供者](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)。  
  
 使用資料集。  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 提供的許多功能與資料集提供的相同，包括在記憶體中的持續性 \(Persistence\)、變更追蹤、資料繫結 \(Data Binding\)，以及將物件序列化為 XML 資料。  如需詳細資訊，請參閱[使用物件](../../../../../docs/framework/data/adonet/ef/working-with-objects.md)。  
  
 如果 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 並未提供應用程式所需的資料集功能，您還是可以使用 [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] 來善用 LINQ 查詢的優勢。  如需詳細資訊，請參閱 [LINQ to DataSet](../../../../../docs/framework/data/adonet/linq-to-dataset.md)。  
  
## 適用於將資料繫結至控制項的應用程式之考量  
 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 可讓您封裝資料集、[!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] 資料來源控制項等這類的資料來源中的資料，然後將使用者介面項目繫結至那些資料控制項。  下列清單說明適用於將控制項繫結至 Entity Framework 資料的考量。  
  
 將資料繫結至控制項。  
 當您查詢概念模型時，[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 會傳回資料做為實體類型執行個體的物件。  這些物件可以直接繫結至控制項，而且此繫結作業支援更新，因此在呼叫 <xref:System.Windows.Forms.DataGridView> 方法時，會自動把對控制項中的資料 \(如 <xref:System.Data.Objects.ObjectContext.SaveChanges%2A> 中的資料列\) 所做的變更儲存至資料庫。  
  
 如果應用程式列舉查詢的結果，以在 <xref:System.Windows.Forms.DataGridView> 或其他支援資料繫結的控制項類型中顯示資料，您則可以把應用程式修改為將控制項繫結至 <xref:System.Data.Objects.ObjectQuery%601> 的結果。  
  
 如需詳細資訊，請參閱[Binding Objects to Controls](http://msdn.microsoft.com/zh-tw/2fd34855-929b-4303-a91e-4bb69d958f2b)。  
  
 [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] 資料來源控制項。  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 包含資料來源控制項，是專為簡化 [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] Web 應用程式中的資料繫結所設計。  如需詳細資訊，請參閱 [Entity Framework Data Source Control](../Topic/EntityDataSource%20Web%20Server%20Control%20Overview.md)。  
  
## 其他考量  
 下列考量可適用於將特定應用程式類型移轉至 Entity Framework 的情況。  
  
 公開資料服務的應用程式。  
 以 Windows Communication Foundation \(WCF\) 為架構的 Web 服務和應用程式使用 XML 要求\/回應訊息格式公開來自基礎資料來源的資料。  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 使用二進位、XML 或 WCF 資料合約序列化 \(Serialization\) 支援實體物件的序列化。  二進位和 WCF 序列化都支援物件圖形的完整序列化。  如需詳細資訊，請參閱 [Building N\-Tier Applications](http://msdn.microsoft.com/zh-tw/9439d2ba-6b5f-44e8-be65-8a442d922cbb)。  
  
 使用 XML 資料的應用程式。  
 物件序列化能讓您建立 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 資料服務。  這些服務為使用 XML 資料的應用程式提供資料，例如以 AJAX 為基礎的網際網路應用程式。  在這些情況下，請考慮使用 [!INCLUDE[ssAstoria](../../../../../includes/ssastoria-md.md)]。  這些資料服務是以實體資料模型為基礎，並且使用標準具像狀態傳輸 \(Representational State Transfer，REST\) HTTP 動作 \(如 GET、PUT 和 POST\) 來提供實體資料的動態存取。  如需詳細資訊，請參閱 [WCF Data Services 4.5](../../../../../docs/framework/data/wcf/index.md)。  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 不支援原生 XML 資料型別，  亦即將實體對應至具有 XML 資料行的資料表時，XML 資料行的對等實體屬性會是字串。  您可以中斷物件的連接，而且將其序列化為 XML。  如需詳細資訊，請參閱[Serializing Objects](http://msdn.microsoft.com/zh-tw/06c77f9b-5b2e-4c78-b3e3-8c148ba0ea99)。  
  
 如果應用程式需要有查詢 XML 資料的功能，您還是可以使用 LINQ to XML 來善用 LINQ 查詢的優勢。  如需詳細資訊，請參閱 [LINQ to XML](../../../../../ocs/visual-basic/programming-guide/concepts/linq/linq-to-xml.md)。  
  
 維護狀態的應用程式。  
 [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] Web 應用程式必須經常維護 Web 網頁或使用者工作階段 \(Session\) 的狀態。  <xref:System.Data.Objects.ObjectContext> 執行個體中的物件可存放於伺服器上的用戶端檢視狀態或工作階段檢視狀態內，以便之後擷取或重新附加至新的物件內容。  如需詳細資訊，請參閱[Attaching and Detaching Objects](http://msdn.microsoft.com/zh-tw/41d5c1ef-1b78-4502-aa10-7e1438d62d23)。  
  
## 請參閱  
 [部署考量因素](../../../../../docs/framework/data/adonet/ef/deployment-considerations.md)   
 [Entity Framework 詞彙](../../../../../docs/framework/data/adonet/ef/terminology.md)