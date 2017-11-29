---
title: "ICorProfilerCallback::ObjectAllocated 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectAllocated
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a7e67e6085db4b73ca39688935767072ceadb68e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="9b8a3-102">ICorProfilerCallback::ObjectAllocated 方法</span><span class="sxs-lookup"><span data-stu-id="9b8a3-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="9b8a3-103">通知分析工具，為物件配置在堆積中的記憶體。</span><span class="sxs-lookup"><span data-stu-id="9b8a3-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b8a3-104">語法</span><span class="sxs-lookup"><span data-stu-id="9b8a3-104">Syntax</span></span>  
  
```  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b8a3-105">參數</span><span class="sxs-lookup"><span data-stu-id="9b8a3-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="9b8a3-106">[in]配置記憶體的物件識別碼。</span><span class="sxs-lookup"><span data-stu-id="9b8a3-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="9b8a3-107">[in]為的類別的物件執行個體識別碼。</span><span class="sxs-lookup"><span data-stu-id="9b8a3-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b8a3-108">備註</span><span class="sxs-lookup"><span data-stu-id="9b8a3-108">Remarks</span></span>  
 <span data-ttu-id="9b8a3-109">`ObjectedAllocated`不會從堆疊或 unmanaged 的記憶體配置呼叫方法。</span><span class="sxs-lookup"><span data-stu-id="9b8a3-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="9b8a3-110">`classId`參數可以參考尚未載入的 managed 程式碼中的類別。</span><span class="sxs-lookup"><span data-stu-id="9b8a3-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="9b8a3-111">分析工具將會收到該類別的類別載入回呼之後立即`ObjectAllocated`回呼。</span><span class="sxs-lookup"><span data-stu-id="9b8a3-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b8a3-112">需求</span><span class="sxs-lookup"><span data-stu-id="9b8a3-112">Requirements</span></span>  
 <span data-ttu-id="9b8a3-113">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9b8a3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b8a3-114">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9b8a3-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9b8a3-115">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b8a3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b8a3-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b8a3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b8a3-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9b8a3-117">See Also</span></span>  
 [<span data-ttu-id="9b8a3-118">ICorProfilerCallback 介面</span><span class="sxs-lookup"><span data-stu-id="9b8a3-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="9b8a3-119">ClassLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="9b8a3-119">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)  
 [<span data-ttu-id="9b8a3-120">ClassLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="9b8a3-120">ClassLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)