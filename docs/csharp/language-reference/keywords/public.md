---
title: public (C# 參考)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 197ef4a2a8544d439b0c34ec14bb7752b760ea06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="public-c-reference"></a>public (C# 參考)
`public` 關鍵字是類型和類型成員的存取修飾詞。 公用存取是最寬鬆的存取層級。 不會限制存取公用成員，如此範例所示︰  
  
```  
class SampleClass  
{  
    public int x; // No access restrictions.  
}  
```  
  
 如需詳細資訊，請參閱[存取修飾詞](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)和[存取範圍層級](../../../csharp/language-reference/keywords/accessibility-levels.md)。  
  
## <a name="example"></a>範例  
 在下列範例中，宣告兩個類別：`PointTest` 和 `MainClass`。 `PointTest`的公用成員 `x` 和 `y` 直接存取自 `MainClass`。  
  
 [!code-csharp[csrefKeywordsModifiers#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/public_1.cs)]  
  
 如果您將 `public` 存取層級變更為 [private](../../../csharp/language-reference/keywords/private.md) 或 [protected](../../../csharp/language-reference/keywords/protected.md)，則會收到錯誤訊息：  
  
 'PointTest.y' 的保護層級導致無法對其進行存取。  
  
## <a name="c-language-specification"></a>C# 語言規格  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [C# 參考](../../../csharp/language-reference/index.md)  
 [C# 程式設計指南](../../../csharp/programming-guide/index.md)  
 [存取修飾詞](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [C# 關鍵字](../../../csharp/language-reference/keywords/index.md)  
 [存取修飾詞](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [存取範圍層級](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [修飾詞](../../../csharp/language-reference/keywords/modifiers.md)  
 [private](../../../csharp/language-reference/keywords/private.md)  
 [protected](../../../csharp/language-reference/keywords/protected.md)  
 [internal](../../../csharp/language-reference/keywords/internal.md)
