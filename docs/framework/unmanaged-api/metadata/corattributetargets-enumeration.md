---
title: "CorAttributeTargets 列舉"
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
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4ce701c026b4e977c376b6e6f0f342b031634e38
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="corattributetargets-enumeration"></a>CorAttributeTargets 列舉
指定有效套用屬性的應用程式項目。  
  
## <a name="syntax"></a>語法  
  
```  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =   
        catAssembly | catModule | catClass | catStruct |   
        catEnum | catConstructor | catMethod | catProperty |   
        catField | catEvent | catInterface | catParameter |   
        catDelegate | catGenericParameter,  
  
    catClassMembers        =   
        catClass | catStruct | catEnum | catConstructor |   
        catMethod | catProperty | catField | catEvent |   
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a>成員  
  
|成員|描述|  
|------------|-----------------|  
|`catAssembly`|屬性可以套用至組件中。|  
|`catModule`|屬性可以套用至可攜式執行檔 （.dll 或.exe） 模組。|  
|`catClass`|屬性可以套用至類別。|  
|`catStruct`|屬性可以套用至結構。也就是說，類型的值。|  
|`catEnum`|屬性可以套用至列舉。|  
|`catConstructor`|屬性可以套用至建構函式。|  
|`catMethod`|屬性可以套用至方法。|  
|`catProperty`|屬性可以套用至屬性。|  
|`catField`|屬性可以套用至欄位。|  
|`catEvent`|屬性可以套用到的事件。|  
|`catInterface`|屬性可以套用至介面。|  
|`catParameter`|屬性可以套用至參數。|  
|`catDelegate`|屬性可以套用的委派。|  
|`catGenericParameter`|屬性可以套用至泛型參數。|  
|`catAll`|屬性可以套用至任何應用程式項目。|  
|`catClassMembers`|屬性可以套用至類別的成員。|  
  
## <a name="remarks"></a>備註  
 `CorAttributeTargets`列舉值可以與慣用的組合，將位元 OR 運算結合。  
  
 `CorAttributeTargets`與 managed<xref:System.AttributeTargets?displayProperty=nameWithType>列舉型別。  
  
## <a name="requirements"></a>需求  
 **平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** CorHdr.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>請參閱  
 [中繼資料列舉](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
