---
title: "ICLRGCManager::Collect 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager.Collect
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 96f99855654a3a86873ca4623d8617f74030938b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="28957-102">ICLRGCManager::Collect 方法</span><span class="sxs-lookup"><span data-stu-id="28957-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="28957-103">強制執行指定的層代的回收。</span><span class="sxs-lookup"><span data-stu-id="28957-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28957-104">語法</span><span class="sxs-lookup"><span data-stu-id="28957-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="28957-105">參數</span><span class="sxs-lookup"><span data-stu-id="28957-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="28957-106">[in]要收集的層代。</span><span class="sxs-lookup"><span data-stu-id="28957-106">[in] The generation to collect.</span></span> <span data-ttu-id="28957-107">值為-1 會強制所有層代的集合。</span><span class="sxs-lookup"><span data-stu-id="28957-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28957-108">傳回值</span><span class="sxs-lookup"><span data-stu-id="28957-108">Return Value</span></span>  
  
|<span data-ttu-id="28957-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="28957-109">HRESULT</span></span>|<span data-ttu-id="28957-110">描述</span><span class="sxs-lookup"><span data-stu-id="28957-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="28957-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="28957-111">S_OK</span></span>|<span data-ttu-id="28957-112">`Collect`已成功傳回。</span><span class="sxs-lookup"><span data-stu-id="28957-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="28957-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="28957-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="28957-114">Common language runtime (CLR) 尚未載入到處理程序，或 CLR 正在中它無法執行 managed 程式碼，或成功地處理呼叫的狀態。</span><span class="sxs-lookup"><span data-stu-id="28957-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="28957-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="28957-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="28957-116">呼叫已逾時。</span><span class="sxs-lookup"><span data-stu-id="28957-116">The call timed out.</span></span>|  
|<span data-ttu-id="28957-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="28957-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="28957-118">呼叫端未擁有鎖定。</span><span class="sxs-lookup"><span data-stu-id="28957-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="28957-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="28957-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="28957-120">事件已取消時封鎖的執行緒或 fiber 等候它。</span><span class="sxs-lookup"><span data-stu-id="28957-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="28957-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="28957-121">E_FAIL</span></span>|<span data-ttu-id="28957-122">發生未知的嚴重失敗。</span><span class="sxs-lookup"><span data-stu-id="28957-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="28957-123">方法會傳回 E_FAIL 之後，CLR 就不再可用的處理序內。</span><span class="sxs-lookup"><span data-stu-id="28957-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="28957-124">裝載方法的後續呼叫會傳回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="28957-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28957-125">備註</span><span class="sxs-lookup"><span data-stu-id="28957-125">Remarks</span></span>  
 <span data-ttu-id="28957-126">`Collect`方法會強制 CLR 的記憶體回收行程執行回收，不論目前的狀態。</span><span class="sxs-lookup"><span data-stu-id="28957-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28957-127">需求</span><span class="sxs-lookup"><span data-stu-id="28957-127">Requirements</span></span>  
 <span data-ttu-id="28957-128">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28957-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28957-129">**標頭：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="28957-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="28957-130">**程式庫：**包含做為 MSCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="28957-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28957-131">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28957-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28957-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="28957-132">See Also</span></span>  
 [<span data-ttu-id="28957-133">自動管理記憶體</span><span class="sxs-lookup"><span data-stu-id="28957-133">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="28957-134">記憶體回收</span><span class="sxs-lookup"><span data-stu-id="28957-134">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="28957-135">ICLRControl 介面</span><span class="sxs-lookup"><span data-stu-id="28957-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="28957-136">ICLRGCManager 介面</span><span class="sxs-lookup"><span data-stu-id="28957-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="28957-137">CLR 裝載介面</span><span class="sxs-lookup"><span data-stu-id="28957-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="28957-138">裝載介面</span><span class="sxs-lookup"><span data-stu-id="28957-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="28957-139">裝載</span><span class="sxs-lookup"><span data-stu-id="28957-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)