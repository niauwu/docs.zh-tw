---
title: "ICorDebugProcess::IsOSSuspended 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 97c394e3084007227cf157c62a12df3f5cfac8e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessisossuspended-method"></a>ICorDebugProcess::IsOSSuspended 方法
取得值，指出指定的執行緒是否已暫止偵錯工具停止此處理序的結果。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
#### <a name="parameters"></a>參數  
 `threadID`  
 [in]有問題的執行緒識別碼。  
  
 `pbSuspended`  
 [out]為的布林值的指標`true`如果指定的執行緒已經暫止的; 否則為 *`pbSuspended`是`false`。  
  
## <a name="remarks"></a>備註  
 指定的執行緒的 Win32 時指定的執行緒已暫停偵錯工具停止此處理序的結果，暫停計數就會累加 1。 偵錯工具使用者介面 (UI) 可能會想要取得這項資訊納入考量，如果它顯示作業系統 (OS) 暫停的使用者執行緒計數。  
  
 `IsOSSuspended`方法有意義的 unmanaged 偵錯內容中。 Managed 偵錯期間，執行緒會以合作方式暫止，而非 OS 暫停。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** CorDebug.idl、 CorDebug.h  
  
 **程式庫：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
