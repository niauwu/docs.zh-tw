---
title: 如何：建立應用程式定義域
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 366dbea0f9559cdeccd2e126e4a3e913fb5ba23d
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-an-application-domain"></a>如何：建立應用程式定義域
Common Language Runtime Host 會在有需要時自動建立應用程式定義域。 不過，您可以建立自己的應用程式定義域，將它們載入您想要自行管理的組件中。 您也可以建立要從中執行程式碼的應用程式定義域。  
  
 使用 <xref:System.AppDomain?displayProperty=nameWithType> 類別的其中一個多載 **CreateDomain** 方法，建立新的應用程式定義域。 您可以提供應用程式定義域的名稱，並依該名稱參考它。  
  
 以下範例會建立新的應用程式定義域並指派名稱 `MyDomain`，然後將主機網域和新建子應用程式定義域的名稱列印至主控台。  
  
## <a name="example"></a>範例  
 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## <a name="see-also"></a>請參閱  
 [使用應用程式定義域設計程式](application-domains.md#programming-with-application-domains)  
 [使用應用程式定義域](../../../docs/framework/app-domains/use.md)
