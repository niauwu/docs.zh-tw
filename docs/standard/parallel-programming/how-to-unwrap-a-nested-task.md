---
title: "如何：解除包裝巢狀工作"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 06d54efe5c8bac58746a1e01a194af55fde901b1
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-unwrap-a-nested-task"></a>如何：解除包裝巢狀工作
您可以從方法傳回工作，接著等待或繼續該工作，如下列範例所示：  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 在上述範例中，<xref:System.Threading.Tasks.Task%601.Result%2A> 屬性是 `string` 類型 (Visual Basic 中為 `String`)。  
  
 不過，在某些情況下，您可能想要在另一個工作內建立工作，然後傳回巢狀的工作。 在此情況下，封閉式工作的 `TResult` 本身就是工作。 在下列範例中，Result 屬性在 C# 中為 `Task<Task<string>>`，在 Visual Basic 中則為 `Task(Of Task(Of String))`。  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 雖然可以撰寫程式碼來解除包裝外部工作並擷取原始工作及其 <xref:System.Threading.Tasks.Task%601.Result%2A> 屬性，但這類程式碼不容易編寫，因為您必須處理例外狀況及取消要求。 在此情況下，建議您使用其中一個 <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> 擴充方法，如下列範例所示。  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 使用 <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> 方法可以將任何 `Task<Task>` 或 `Task<Task<TResult>>` (Visual Basic 中為 `Task(Of Task)` 或 `Task(Of Task(Of TResult))`) 轉換為 `Task` 或 `Task<TResult>` (Visual Basic 中為 `Task(Of TResult)`)。 新的工作完全代表內部巢狀工作，並包含取消狀態及所有例外狀況。  
  
## <a name="example"></a>範例  
 下列範例示範如何使用 <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> 擴充方法。  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a>請參閱  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>  
 [以工作為基礎的非同步程式設計](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
