---
title: Null 語意
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 3c4daa5fd37158f1af31f33ba743a56cf76670d8
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2018
---
# <a name="null-semantics"></a>Null 語意
下表提供各個組件的連結[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]文件位置`null`(`Nothing`在 Visual Basic 中) 問題的討論。  
  
|主題|描述|  
|-----------|-----------------|  
|[SQL-CLR 類型不符](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|此主題的 「 Null 語意 」 一節包含三種狀態 SQL 布林值對兩種狀態 common language runtime (CLR) 的討論<xref:System.Boolean>，常值`Nothing`(Visual Basic) 和`null`(C# 中)，以及其他類似問題。|  
|[標準查詢運算子轉譯](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|本主題的「Null 語意」一節描述 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]中的 null 比較語意。|  
|[System.String 方法](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|本主題的「與 .NET 的差異」一節描述 <xref:System.String.LastIndexOf%2A> 傳回 0 即表示字串為 null 或找到的位置為 0 的原因。|  
|[計算數值序列中各值的總和](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|描述如何<xref:System.Linq.Enumerable.Sum%2A>運算子評估為`null`(`Nothing`在 Visual Basic 中) 而不是 0，只包含 null 的序列或空的序列。|  
  
## <a name="see-also"></a>另請參閱  
 [資料類型和函式](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
