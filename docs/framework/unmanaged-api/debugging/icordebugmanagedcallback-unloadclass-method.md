---
title: "ICorDebugManagedCallback::UnloadClass 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.UnloadClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e034f6950cc9d77ef4db350475379aa5c497f7f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="817c7-102">ICorDebugManagedCallback::UnloadClass 方法</span><span class="sxs-lookup"><span data-stu-id="817c7-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="817c7-103">表示正在卸載的類別會告知偵錯工具。</span><span class="sxs-lookup"><span data-stu-id="817c7-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="817c7-104">語法</span><span class="sxs-lookup"><span data-stu-id="817c7-104">Syntax</span></span>  
  
```  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="817c7-105">參數</span><span class="sxs-lookup"><span data-stu-id="817c7-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="817c7-106">[in]表示包含類別的應用程式定義域的 ICorDebugAppDomain 物件指標。</span><span class="sxs-lookup"><span data-stu-id="817c7-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="817c7-107">[in]表示類別 ICorDebugClass 物件的指標。</span><span class="sxs-lookup"><span data-stu-id="817c7-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="817c7-108">備註</span><span class="sxs-lookup"><span data-stu-id="817c7-108">Remarks</span></span>  
 <span data-ttu-id="817c7-109">類別不應該參考此呼叫之後。</span><span class="sxs-lookup"><span data-stu-id="817c7-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="817c7-110">需求</span><span class="sxs-lookup"><span data-stu-id="817c7-110">Requirements</span></span>  
 <span data-ttu-id="817c7-111">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="817c7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="817c7-112">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="817c7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="817c7-113">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="817c7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="817c7-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="817c7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="817c7-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="817c7-115">See Also</span></span>  
 [<span data-ttu-id="817c7-116">LoadClass 方法</span><span class="sxs-lookup"><span data-stu-id="817c7-116">LoadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)  
 [<span data-ttu-id="817c7-117">ICorDebugManagedCallback 介面</span><span class="sxs-lookup"><span data-stu-id="817c7-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)