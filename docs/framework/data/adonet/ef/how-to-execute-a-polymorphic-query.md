---
title: "如何：執行多型查詢"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3f2a51276568371c48647557f286ec60ac6531b7
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-execute-a-polymorphic-query"></a>如何：執行多型查詢
本主題示範如何執行多型[!INCLUDE[esql](../../../../../includes/esql-md.md)]查詢使用[OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md)運算子。  
  
### <a name="to-run-the-code-in-this-example"></a>執行此範例中的程式碼  
  
1.  新增[School 模型](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac)至您的專案，並設定您的專案使用 Entity Framework。 如需詳細資訊，請參閱[How to： 使用實體資料模型精靈](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)。  
  
2.  在應用程式的字碼頁中加入下列 `using` 陳述式 (在 Visual Basic 中為 `Imports`)：  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  修改要遵循的步驟中有資料表每個 hierrachy 繼承的概念模型[逐步解說： 對應繼承： 每個階層的資料表](http://msdn.microsoft.com/library/49b685cf-9db8-4d6d-b885-8837ed238f55)。  
  
## <a name="example"></a>範例  
 下列範例會使用 OFTYPE 運算子，從 `OnsiteCourses` 的集合中取得並顯示只有 `Courses` 的集合。  
  
 [!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
 [!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]  
  
## <a name="see-also"></a>請參閱  
 [Entity Framework 的 EntityClient 提供者](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
 [Entity SQL 語言](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
