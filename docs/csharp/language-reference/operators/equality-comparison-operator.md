---
title: == 運算子 (C# 參考)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ca22846325968519a1f7625461867c0d83a1a9f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>== 運算子 (C# 參考)
對於預先定義的實值型別，等號比較運算子 (`==`) 在運算元相等時傳回 true；否則傳回 `false`。 對於 [string](../../../csharp/language-reference/keywords/string.md) 以外的參考型別，若兩個運算元參考到同一物件，`==` 會傳回 `true`。 對於 `string` 類型，`==` 會比較字串的值。  
  
## <a name="remarks"></a>備註  
 使用者定義的實值型別可以多載 `==` 運算子 (請參閱 [operator](../../../csharp/language-reference/keywords/operator.md))。 使用者定義的參考型別也可以，不過 `==` 對預先定義和使用者定義之參考型別的預設運作方式會如上所述。 如果多載 `==`，也必須多載 [!=](../../../csharp/language-reference/operators/not-equal-operator.md)。 整數類資料類型上的作業通常允許用於列舉型別。  
  
## <a name="example"></a>範例  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a>另請參閱  
 [C# 參考](../../../csharp/language-reference/index.md)  
 [C# 程式設計指南](../../../csharp/programming-guide/index.md)  
 [C# 運算子](../../../csharp/language-reference/operators/index.md)
