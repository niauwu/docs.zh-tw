---
title: 巢狀類型 (C# 程式設計手冊)
ms.date: 07/10/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ab13c68b638062ab89c90dbfc51b51b8d72d3bde
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="nested-types-c-programming-guide"></a>巢狀類型 (C# 程式設計手冊)
在 [class](../../../csharp/language-reference/keywords/class.md) 或 [struct](../../../csharp/language-reference/keywords/struct.md) 內定義的類型稱為巢狀型別。 例如:   
  
[!code-csharp[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
不論外部類型是 class 或 struct，巢狀型別都預設為 [private](../../../csharp/language-reference/keywords/private.md)；它們只能從其包含類型中進行存取。 在上述範例中，外部類型無法存取 `Nested` 類別。 

您也可以指定[存取修飾詞](../../language-reference/keywords/access-modifiers.md)來定義巢狀型別的存取範圍，如下所示：

- 巢狀類型的**類別**可以[公用](../../../csharp/language-reference/keywords/public.md)，[保護](../../../csharp/language-reference/keywords/protected.md)，[內部](../../../csharp/language-reference/keywords/internal.md)，[保護內部](../../../csharp/language-reference/keywords/protected-internal.md)，[私人](../../../csharp/language-reference/keywords/private.md)或[受保護的私用](../../../csharp/language-reference/keywords/private-protected.md)。 

   不過，定義`protected`，`protected internal`或`private protected`巢狀類別內[密封類別](../../language-reference/keywords/sealed.md)會產生編譯器警告[CS0628](../../misc/cs0628.md)，「 新的 protected 的成員宣告在密封類別中 」。
  
- **struct** 的巢狀型別可以是 [public](../../../csharp/language-reference/keywords/public.md)、[internal](../../../csharp/language-reference/keywords/internal.md) 或 [private](../../../csharp/language-reference/keywords/private.md)。
  
下列範例會將 `Nested` 類別設為 public：
  
[!code-csharp[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]  
  
 巢狀型別或內部類型可存取包含類型或外部類型。 若要存取包含類型，請將它當作引數傳遞至巢狀型別的建構函式。 例如:   
  
 [!code-csharp[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]  
  
 巢狀型別可以存取其包含型別可存取的所有成員。 它可存取包含型別的 private 和 protected 成員，包括任何繼承的 protected 成員。  
  
 在先前的宣告，`Nested` 類別的完整名稱為 `Container.Nested`。 這是用來建立巢狀類別新執行個體的名稱，如下所示：  
  
 [!code-csharp[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]  
  
## <a name="see-also"></a>另請參閱  
 [C# 程式設計指南](../../../csharp/programming-guide/index.md)  
 [類別和結構](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [存取修飾詞](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [建構函式](../../../csharp/programming-guide/classes-and-structs/constructors.md)
