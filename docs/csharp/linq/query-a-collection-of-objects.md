---
title: 查詢物件的集合
description: 如何查詢集合。
keywords: .NET、.NET Core、C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.openlocfilehash: a62e5c6324d15376f1b42ad078eeb883b05ef14f
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/28/2018
---
# <a name="query-a-collection-of-objects"></a>查詢物件的集合
這個範例示範如何對 `Student` 物件清單執行簡單查詢。 每個 `Student` 物件都包含學生的一些基本資訊，以及一份代表學生四次考試分數的清單。  
  
 這個應用程式作為本節中使用相同 `students` 資料來源的許多其他範例的架構。  
  
## <a name="example"></a>範例  
 下列查詢會傳回第一次考試分數等於或高於 90 的學生。  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
 此查詢是刻意簡單，好讓您進行體驗。 例如，您可以在 `where` 子句中嘗試多個條件，或使用 `orderby` 子句來排序結果。  
  

## <a name="see-also"></a>另請參閱  
 [LINQ 查詢運算式](index.md)  
 [字串內插補點](../language-reference/tokens/interpolated.md)
