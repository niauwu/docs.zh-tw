---
title: 使用權限遭拒 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c5d7965ebd42cb3e56d66966d035be9ba3d3957c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="permission-denied-visual-basic"></a>使用權限遭拒 (Visual Basic)
嘗試寫入防寫保護的磁碟，或存取已鎖定的檔案。  
  
## <a name="to-correct-this-error"></a>更正這個錯誤  
  
1.  若要開啟防寫保護的檔案，請變更檔案的防寫保護屬性。  
  
2.  請確定其他處理序不會鎖定檔案，並等待直到其他處理序釋放它為止，開啟檔案。  
  
3.  若要存取登錄，請檢查您的使用者權限包含這種類型的登錄存取權。  
  
## <a name="see-also"></a>另請參閱  
 [錯誤類型](../../../visual-basic/programming-guide/language-features/error-types.md)
