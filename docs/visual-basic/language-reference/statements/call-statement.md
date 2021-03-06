---
title: Call 陳述式 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c72450fd6f931f36f640d3e384a6fd38d57a7a23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="call-statement-visual-basic"></a>Call 陳述式 (Visual Basic)
控制權轉移到`Function`， `Sub`，或動態連結程式庫 (DLL) 程序。  
  
## <a name="syntax"></a>語法  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>組件  
 `procedureName`  
 必要項。 若要呼叫的程序名稱。  
  
 `argumentList`  
 選擇項。 變數或運算式表示呼叫時，會傳遞至程序的引數的清單。 以逗號分隔多個引數。 如果您包含`argumentList`，您必須將它括在括號中。  
  
## <a name="remarks"></a>備註  
 您可以使用`Call`關鍵字時呼叫的程序。 大部分的程序呼叫中，您不需要使用這個關鍵字。  
  
 您通常會使用`Call`被呼叫的運算式無法啟動的識別項時的關鍵字。 使用`Call`給其他用途的關鍵字時，不建議。  
  
 此程序傳回值，如果`Call`陳述式便會捨棄它。  
  
## <a name="example"></a>範例  
 下列程式碼顯示兩個範例其中`Call`關鍵字，才能呼叫程序。 在這兩個範例中，被呼叫的運算式不會啟動識別碼。  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/call-statement_1.vb)]  
  
## <a name="see-also"></a>另請參閱  
 [Function 陳述式](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub 陳述式](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Declare 陳述式](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Lambda 運算式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
