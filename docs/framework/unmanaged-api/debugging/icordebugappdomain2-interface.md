---
title: ICorDebugAppDomain2 Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain2
helpviewer_keywords: ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ebd1e504cbf2f74ad82e7fea6b6c3f355a1bda34
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain2-interface1"></a><span data-ttu-id="92f39-102">ICorDebugAppDomain2 Interface1</span><span class="sxs-lookup"><span data-stu-id="92f39-102">ICorDebugAppDomain2 Interface1</span></span>
<span data-ttu-id="92f39-103">提供方法來處理陣列、 指標、 函式指標和參考型別。</span><span class="sxs-lookup"><span data-stu-id="92f39-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="92f39-104">這個介面是 ICorDebugAppDomain 介面的擴充功能。</span><span class="sxs-lookup"><span data-stu-id="92f39-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="92f39-105">方法</span><span class="sxs-lookup"><span data-stu-id="92f39-105">Methods</span></span>  
  
|<span data-ttu-id="92f39-106">方法</span><span class="sxs-lookup"><span data-stu-id="92f39-106">Method</span></span>|<span data-ttu-id="92f39-107">說明</span><span class="sxs-lookup"><span data-stu-id="92f39-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="92f39-108">GetArrayOrPointerType 方法</span><span class="sxs-lookup"><span data-stu-id="92f39-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="92f39-109">取得指定的型別，或是指標或參考指定之類型的陣列。</span><span class="sxs-lookup"><span data-stu-id="92f39-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="92f39-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="92f39-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="92f39-111">取得具有指定簽章的函式指標。</span><span class="sxs-lookup"><span data-stu-id="92f39-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92f39-112">備註</span><span class="sxs-lookup"><span data-stu-id="92f39-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92f39-113">這個介面不支援跨電腦或跨處理序的遠端呼叫。</span><span class="sxs-lookup"><span data-stu-id="92f39-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92f39-114">需求</span><span class="sxs-lookup"><span data-stu-id="92f39-114">Requirements</span></span>  
 <span data-ttu-id="92f39-115">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="92f39-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92f39-116">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92f39-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92f39-117">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92f39-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92f39-118">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92f39-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92f39-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="92f39-119">See Also</span></span>  
 [<span data-ttu-id="92f39-120">偵錯介面</span><span class="sxs-lookup"><span data-stu-id="92f39-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)