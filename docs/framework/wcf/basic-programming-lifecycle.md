---
title: 基本程式設計週期
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
caps.latest.revision: 36
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ff735a8caf1fbaff636f94eee366b20c33d8f331
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2018
---
# <a name="basic-programming-lifecycle"></a>基本程式設計週期
不管應用程式位於同一部電腦、位於網際網路的個別電腦上，還是位於不同的應用程式平台，[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 都可以讓應用程式彼此通訊。 本主題將概要說明建置 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 應用程式需要執行的工作。 可用的範例應用程式，請參閱[入門教學課程](../../../docs/framework/wcf/getting-started-tutorial.md)。  
  
## <a name="the-basic-tasks"></a>基本工作  
 要執行的基本工作依序為：  
  
1.  定義服務合約。 服務合約可指定服務簽章、服務所交換的資料，以及其他合約所需的資料。 如需詳細資訊，請參閱[設計服務合約](../../../docs/framework/wcf/designing-service-contracts.md)。  
  
2.  實作合約。 若要實作合約，請建立可實作合約的類別，然後指定執行階段應該具備的自訂行為。 如需詳細資訊，請參閱[實作服務合約](../../../docs/framework/wcf/implementing-service-contracts.md)。  
  
3.  指定端點與其他行為資訊來設定服務。 如需詳細資訊，請參閱[設定 Services](../../../docs/framework/wcf/configuring-services.md)。  
  
4.  裝載服務。 如需詳細資訊，請參閱[裝載服務](../../../docs/framework/wcf/hosting-services.md)。  
  
5.  建置用戶端應用程式。 如需詳細資訊，請參閱[建置用戶端](../../../docs/framework/wcf/building-clients.md)。  
  
 儘管本章節的主題遵循此順序進行說明，在某些情況下並不會從第一個步驟開始。 例如，如果您想要為既有的服務建置用戶端，請從步驟 5 開始。 或者，如果您要建置其他人將使用的服務，則可以跳過步驟 5。  
  
 一旦您熟悉開發服務合約時，您也可以讀取[擴充性簡介](../../../docs/framework/wcf/introduction-to-extensibility.md)。 如果您有與服務的問題，請檢查[WCF 疑難排解快速入門](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)若要查看其他人是否具有相同或類似的問題。  
  
## <a name="see-also"></a>另請參閱  
 [履行服務合約](../../../docs/framework/wcf/implementing-service-contracts.md)
