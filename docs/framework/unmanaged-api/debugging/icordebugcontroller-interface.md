---
title: ICorDebugController Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController
helpviewer_keywords: ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b1484d6bcfa77b8bf5fe45b2f83d5dcbff02f907
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontroller-interface1"></a><span data-ttu-id="572a5-102">ICorDebugController Interface1</span><span class="sxs-lookup"><span data-stu-id="572a5-102">ICorDebugController Interface1</span></span>
<span data-ttu-id="572a5-103">表示可以控制程式碼執行內容的範圍 (<xref:System.Diagnostics.Process> 或 <xref:System.AppDomain> 其中一項)。</span><span class="sxs-lookup"><span data-stu-id="572a5-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="572a5-104">方法</span><span class="sxs-lookup"><span data-stu-id="572a5-104">Methods</span></span>  
  
|<span data-ttu-id="572a5-105">方法</span><span class="sxs-lookup"><span data-stu-id="572a5-105">Method</span></span>|<span data-ttu-id="572a5-106">說明</span><span class="sxs-lookup"><span data-stu-id="572a5-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="572a5-107">這個方法已過時。</span><span class="sxs-lookup"><span data-stu-id="572a5-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="572a5-108">這個方法已過時。</span><span class="sxs-lookup"><span data-stu-id="572a5-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="572a5-109">Continue 方法</span><span class="sxs-lookup"><span data-stu-id="572a5-109">Continue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|<span data-ttu-id="572a5-110">之後繼續執行的 managed 執行緒的呼叫[icordebugcontroller:: Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)。</span><span class="sxs-lookup"><span data-stu-id="572a5-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="572a5-111">Detach 方法</span><span class="sxs-lookup"><span data-stu-id="572a5-111">Detach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|<span data-ttu-id="572a5-112">從處理序或應用程式網域偵錯工具會中斷連結。</span><span class="sxs-lookup"><span data-stu-id="572a5-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="572a5-113">EnumerateThreads 方法</span><span class="sxs-lookup"><span data-stu-id="572a5-113">EnumerateThreads Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="572a5-114">取得作用中的 managed 執行緒處理序中的列舉值。</span><span class="sxs-lookup"><span data-stu-id="572a5-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="572a5-115">HasQueuedCallbacks 方法</span><span class="sxs-lookup"><span data-stu-id="572a5-115">HasQueuedCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="572a5-116">取得值，指出是否針對指定的執行緒目前佇列任何受管理的回呼。</span><span class="sxs-lookup"><span data-stu-id="572a5-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="572a5-117">IsRunning 方法</span><span class="sxs-lookup"><span data-stu-id="572a5-117">IsRunning Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|<span data-ttu-id="572a5-118">取得值，指出是否在處理程序中的執行緒目前正在自由。</span><span class="sxs-lookup"><span data-stu-id="572a5-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="572a5-119">SetAllThreadsDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="572a5-119">SetAllThreadsDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="572a5-120">設定偵錯狀態的所有 managed 執行緒處理序中。</span><span class="sxs-lookup"><span data-stu-id="572a5-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="572a5-121">Stop 方法</span><span class="sxs-lookup"><span data-stu-id="572a5-121">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|<span data-ttu-id="572a5-122">在 managed 程式碼執行處理序中的所有執行緒上執行合作式停止。</span><span class="sxs-lookup"><span data-stu-id="572a5-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="572a5-123">Terminate 方法</span><span class="sxs-lookup"><span data-stu-id="572a5-123">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|<span data-ttu-id="572a5-124">終止與指定的結束代碼的程序。</span><span class="sxs-lookup"><span data-stu-id="572a5-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="572a5-125">備註</span><span class="sxs-lookup"><span data-stu-id="572a5-125">Remarks</span></span>  
 <span data-ttu-id="572a5-126">如果`ICorDebugController`是控制處理程序，其範圍包括所有執行緒的程序。</span><span class="sxs-lookup"><span data-stu-id="572a5-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="572a5-127">如果`ICorDebugController`會控制應用程式定義域的範圍包括該特定應用程式網域的執行緒。</span><span class="sxs-lookup"><span data-stu-id="572a5-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="572a5-128">這個介面不支援跨電腦或跨處理序的遠端呼叫。</span><span class="sxs-lookup"><span data-stu-id="572a5-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="572a5-129">需求</span><span class="sxs-lookup"><span data-stu-id="572a5-129">Requirements</span></span>  
 <span data-ttu-id="572a5-130">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="572a5-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="572a5-131">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="572a5-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="572a5-132">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="572a5-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="572a5-133">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="572a5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="572a5-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="572a5-134">See Also</span></span>  
 [<span data-ttu-id="572a5-135">偵錯介面</span><span class="sxs-lookup"><span data-stu-id="572a5-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)