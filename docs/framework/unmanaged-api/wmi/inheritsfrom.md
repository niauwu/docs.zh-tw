---
title: "[Inheritsfrom] 函式 （Unmanaged API 參考）"
description: "[Inheritsfrom] 函式判斷類別或執行個體是否衍生自特定的父類別。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: InheritsFrom
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: InheritsFrom
helpviewer_keywords: InheritsFrom function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aedeec76f4fabb2f6bd32d7d06eb5a1a5734534e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2017
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="89256-103">[Inheritsfrom] 函式</span><span class="sxs-lookup"><span data-stu-id="89256-103">InheritsFrom function</span></span>
<span data-ttu-id="89256-104">判斷目前的類別或執行個體是否衍生自指定的父類別。</span><span class="sxs-lookup"><span data-stu-id="89256-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="89256-105">語法</span><span class="sxs-lookup"><span data-stu-id="89256-105">Syntax</span></span>  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="89256-106">參數</span><span class="sxs-lookup"><span data-stu-id="89256-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="89256-107">[in]未使用這個參數。</span><span class="sxs-lookup"><span data-stu-id="89256-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="89256-108">[in]指標[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)執行個體。</span><span class="sxs-lookup"><span data-stu-id="89256-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="89256-109">[in]類別的名稱。</span><span class="sxs-lookup"><span data-stu-id="89256-109">[in] The name of the class.</span></span> <span data-ttu-id="89256-110">`wszAncestor`必須指向有效`LPCWSTR`。</span><span class="sxs-lookup"><span data-stu-id="89256-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="89256-111">傳回值</span><span class="sxs-lookup"><span data-stu-id="89256-111">Return value</span></span>

<span data-ttu-id="89256-112">這個函式傳回下列值會定義在*WbemCli.h*標頭檔，或者您可以定義它們以常數的形式在程式碼中：</span><span class="sxs-lookup"><span data-stu-id="89256-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="89256-113">常數</span><span class="sxs-lookup"><span data-stu-id="89256-113">Constant</span></span>  |<span data-ttu-id="89256-114">值</span><span class="sxs-lookup"><span data-stu-id="89256-114">Value</span></span>  |<span data-ttu-id="89256-115">描述</span><span class="sxs-lookup"><span data-stu-id="89256-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="89256-116">0</span><span class="sxs-lookup"><span data-stu-id="89256-116">0</span></span> | <span data-ttu-id="89256-117">目前的物件會繼承`wszAncestor`。</span><span class="sxs-lookup"><span data-stu-id="89256-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="89256-118">1</span><span class="sxs-lookup"><span data-stu-id="89256-118">1</span></span> | <span data-ttu-id="89256-119">目前的物件不是繼承自`wszAncestor`。</span><span class="sxs-lookup"><span data-stu-id="89256-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="89256-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="89256-120">0x80041008</span></span> | <span data-ttu-id="89256-121">`wszAncestor` 為 `null`。</span><span class="sxs-lookup"><span data-stu-id="89256-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="89256-122">備註</span><span class="sxs-lookup"><span data-stu-id="89256-122">Remarks</span></span>

<span data-ttu-id="89256-123">此函式會包裝呼叫[IWbemClassObject::InheritsFrom](https://msdn.microsoft.com/library/aa391452(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="89256-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](https://msdn.microsoft.com/library/aa391452(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="89256-124">需求</span><span class="sxs-lookup"><span data-stu-id="89256-124">Requirements</span></span>  
 <span data-ttu-id="89256-125">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="89256-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89256-126">**標頭：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="89256-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="89256-127">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="89256-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89256-128">請參閱</span><span class="sxs-lookup"><span data-stu-id="89256-128">See also</span></span>  
[<span data-ttu-id="89256-129">WMI 和效能計數器 （Unmanaged API 參考）</span><span class="sxs-lookup"><span data-stu-id="89256-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)