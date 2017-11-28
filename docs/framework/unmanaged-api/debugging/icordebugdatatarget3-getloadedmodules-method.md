---
title: "ICorDebugDataTarget3::GetLoadedModules 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bc4820d2c71830b297ed690c440c90cfff1f9601
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="5c435-102">ICorDebugDataTarget3::GetLoadedModules 方法</span><span class="sxs-lookup"><span data-stu-id="5c435-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="5c435-103">取得到目前為止已載入的模組清單。</span><span class="sxs-lookup"><span data-stu-id="5c435-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c435-104">語法</span><span class="sxs-lookup"><span data-stu-id="5c435-104">Syntax</span></span>  
  
```  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c435-105">參數</span><span class="sxs-lookup"><span data-stu-id="5c435-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="5c435-106">[in] 要求該模組資訊的模組數目。</span><span class="sxs-lookup"><span data-stu-id="5c435-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="5c435-107">[out] 傳回該模組資訊之模組數目的指標。</span><span class="sxs-lookup"><span data-stu-id="5c435-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="5c435-108">[out]陣列的指標[ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)提供下列資訊的物件載入的模組。</span><span class="sxs-lookup"><span data-stu-id="5c435-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c435-109">備註</span><span class="sxs-lookup"><span data-stu-id="5c435-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c435-110">這個方法僅適用於 .NET 原生。</span><span class="sxs-lookup"><span data-stu-id="5c435-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c435-111">需求</span><span class="sxs-lookup"><span data-stu-id="5c435-111">Requirements</span></span>  
 <span data-ttu-id="5c435-112">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5c435-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c435-113">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c435-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c435-114">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c435-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c435-115">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c435-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c435-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5c435-116">See Also</span></span>  
 [<span data-ttu-id="5c435-117">ICorDebugDataTarget3 介面</span><span class="sxs-lookup"><span data-stu-id="5c435-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 [<span data-ttu-id="5c435-118">偵錯介面</span><span class="sxs-lookup"><span data-stu-id="5c435-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)