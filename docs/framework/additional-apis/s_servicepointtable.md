---
title: "ServicePointManager.s_ServicePointTable 欄位"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type: apiref
api_name: System.Net.ServicePointManager.s_ServicePointTable
api_location: System.dll
api_type: Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2f12a8ba4d2b84e5b5d73d26199adf687a95a2df
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="servicepointmanagersservicepointtable-field"></a><span data-ttu-id="13495-102">ServicePointManager.s\_ServicePointTable 欄位</span><span class="sxs-lookup"><span data-stu-id="13495-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="13495-103">`ServicePointManager.s_ServicePointTable`是<xref:System.Collections.Hashtable>包含使用中的 HTTP 連接的清單 (<xref:System.Net.ServicePoint>s) 中<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="13495-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="13495-104">語法</span><span class="sxs-lookup"><span data-stu-id="13495-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="13495-105">`ServicePointManager.s_ServicePointTable`欄位是私用，而且不會直接在您的程式碼中使用它們。</span><span class="sxs-lookup"><span data-stu-id="13495-105">The `ServicePointManager.s_ServicePointTable` field is private and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="13495-106">Microsoft 不支援在實際執行應用程式在任何情況下使用此欄位。</span><span class="sxs-lookup"><span data-stu-id="13495-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="13495-107">需求</span><span class="sxs-lookup"><span data-stu-id="13495-107">Requirements</span></span>

<span data-ttu-id="13495-108">**命名空間：**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="13495-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="13495-109">**組件：**系統 （在 System.dll)</span><span class="sxs-lookup"><span data-stu-id="13495-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="13495-110">**.NET framework 版本：**自 2.0 起可用。</span><span class="sxs-lookup"><span data-stu-id="13495-110">**.NET Framework versions:** Available since 2.0.</span></span>