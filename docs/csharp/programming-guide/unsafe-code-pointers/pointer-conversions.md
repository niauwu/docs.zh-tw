---
title: 指標轉換 (C# 程式設計手冊)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 36589d139c91e04d9e3d8b31281a91c26b85a5d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="pointer-conversions-c-programming-guide"></a>指標轉換 (C# 程式設計手冊)
下表顯示預先定義的隱含指標轉換。 在許多情況下可能會發生隱含轉換，包括方法叫用和指派陳述式。  
  
## <a name="implicit-pointer-conversions"></a>隱含指標轉換  
  
|從|以|  
|----------|--------|  
|任何指標類型|void*|  
|null|任何指標類型|  
  
 明確指標轉換是用來使用 cast 運算式執行轉換，而這項轉換沒有任何隱含轉換。 下表顯示這些轉換。  
  
## <a name="explicit-pointer-conversions"></a>明確指標轉換  
  
|從|以|  
|----------|--------|  
|任何指標類型|任何其他指標類型|  
|sbyte、byte、short、ushort、int、uint、long 或 ulong|任何指標類型|  
|任何指標類型|sbyte、byte、short、ushort、int、uint、long 或 ulong|  
  
## <a name="example"></a>範例  
 在下列範例中，`int` 的指標會轉換為 `byte` 的指標。 請注意，指標會指向變數的最低定址位元組。 當您連續遞增結果時 (大小最多為 `int` (4 個位元組))，可以顯示變數的剩餘位元組。  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]  
  
## <a name="see-also"></a>另請參閱  
 [C# 程式設計指南](../../../csharp/programming-guide/index.md)  
 [指標運算式](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [指標型別](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [型別](../../../csharp/language-reference/keywords/types.md)  
 [Unsafe.DangerousAPI](../../../csharp/language-reference/keywords/unsafe.md)  
 [fixed 陳述式](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
