---
title: 其他類別庫和 API
ms.custom: ''
ms.date: 01/29/2018
ms.prod: .net-framework-oob
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
caps.latest.revision: 12
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d9ceb1ad24d4ba87fab7713ba61fed91eef26c4d
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/01/2018
---
# <a name="additional-class-libraries-and-apis"></a>其他類別庫和 API

由於 .NET Framework 會持續演變，因此為了改善跨平台開發工作或讓客戶早點採用新功能，我們會不定期 (Out of Band，OOB) 發行新功能。 本主題列出有提供文件的 OOB 專案。  
  
除此之外，某些程式庫會以 .NET Framework 的特定平台或實作為目標。 例如，<xref:System.Text.CodePagesEncodingProvider>類別使字碼頁編碼方式可使用.NET Framework 開發 UWP 應用程式。 本主題也會列出這些程式庫。  
  
## <a name="oob-projects"></a>OOB 專案
  
| 專案 | 描述 |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | 提供具備執行緒安全且保證不會再變更其內容的集合。 |
| <xref:System.Net.Http.WinHttpHandler> | 提供以 Windows 的 WinHTTP 介面為基礎之 <xref:System.Net.Http.HttpClient> 的訊息處理常式。 |
| [System.Numerics.Vectors (英文)](https://msdn.microsoft.com/library/mt452176.aspx) | 提供可利用 SIMD 硬體加速的向量類型程式庫。| 
| <xref:System.Threading.Tasks.Dataflow> | TPL 資料流程程式庫提供資料流程元件，來協助增加啟用並行的應用程式之穩定性。 |  

## <a name="platform-specific-libraries"></a>平台特定程式庫
  
| 專案 | 描述 |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | 擴充<xref:System.Text.EncodingProvider>供通用 Windows 平台為目標的應用程式程式碼頁編碼方式的類別。 |  
  
## <a name="private-apis"></a>私人 API  

這些 API 支援產品基礎結構，而且不適合/不支援直接從程式碼使用。  
  
| API 名稱 |
| -------- |
| [System.Net.Connection 類別](../../../docs/framework/additional-apis/connection.md) |
| [System.Net.Connection.m\_WriteList 欄位](../../../docs/framework/additional-apis/m_writelist.md) |
| [System.Net.ConnectionGroup 類別](../../../docs/framework/additional-apis/connectiongroup.md) |
| [System.Net.ConnectionGroup.m\_ConnectionList 欄位](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [System.Net.CoreResponseData 類別](../../../docs/framework/additional-apis/coreresponsedata.md) |
| [System.Net.CoreResponseData.m\_ResponseHeaders 欄位](../../../docs/framework/additional-apis/coreresponsedata_m_responseheaders.md) |
| [System.Net.CoreResponseData.m\_StatusCode 欄位](../../../docs/framework/additional-apis/coreresponsedata_m_statuscode.md) |
| [System.Net.HttpWebRequest。\_AutoRedirects 欄位](../../../docs/framework/additional-apis/_autoredirects.md) |
| [System.Net.HttpWebRequest。\_CoreResponse 欄位](../../../docs/framework/additional-apis/httpwebrequest__coreresponse.md) |
| [System.Net.HttpWebRequest。\_HttpResponse 欄位](../../../docs/framework/additional-apis/_httpresponse.md) |
| [System.Net.ServicePoint.m\_ConnectionGroupList Field](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [System.Net.ServicePointManager.s\_ServicePointTable 欄位](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [System.Windows.Forms.Design.DataMemberFieldEditor 類別](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [System.Windows.Forms.Design.DataMemberListEditor 類別](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a>另請參閱

[.NET Framework 和不定期發行](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
