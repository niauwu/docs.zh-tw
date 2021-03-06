---
title: 值 (F#)
description: '了解如何在 F # 中的值為具有特定類型的數量。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: b40e4a0409a9161a4ef48c8d4ad82b4da346538e
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2018
---
# <a name="values"></a>值

F# 中的值是具有特定類型的數量；值可以是整數或浮點數、字元或文字、清單、序列、陣列、元組、差別聯集、記錄、類別類型或函式值。


## <a name="binding-a-value"></a>繫結值
「繫結」一詞表示建立名稱與定義的關聯。 `let` 關鍵字會繫結值，如下列範例所示：

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet601.fs)]

值的類型是從定義推斷的。 若為基本類型 (例如整數或浮點數)，則是從常值的類型來決定類型。 因此，在上述範例中，編譯器推斷 `b` 的類型是 `unsigned int`，而推斷 `a` 的類型是 `int`。 函式值的類型是從函式主體中的傳回值決定。 如需函式值類型的詳細資訊，請參閱[函式](../functions/index.md)。 如需常值型別的詳細資訊，請參閱[常值](../literals.md)。


## <a name="why-immutable"></a>使用不可變的原因
不可變的值是在程式執行過程中無法變更的值。 若您習慣使用 C++、Visual Basic 或 C# 等語言，F# 首重不可變的值，而不是程式執行期間可指派新值的變數，這可能讓您訝異。 不可變的資料是函式程式設計的重要項目。 在多執行緒環境中，難以管理可由許多不同的執行緒變更的共用可變變數。 此外，對於可變變數，有時候難以判斷變數是否會在傳遞至另一個函式時變更。

在純函式語言中，沒有變數，而且函式只作為數學函式。 程序語言中的程式碼使用變數指派來變更值，而在函式語言中的對等程式碼則有作為輸入的不可變值、不可變的函式，以及作為輸出的不同不可變值。 如此在數學方面嚴謹的程度，可以讓程式的行為更符合預期。 如此一來，編譯器就能更嚴格地檢查程式碼，並且在最佳化時更有效率，也有助於程式開發人員更容易了解及撰寫正確程式碼。 所以，比起一般程序程式碼，偵錯函式程式碼也更為容易。

F# 不是純函式語言，但完全支援函式程式設計。 使用不可變的值是良好做法，因為這麼做可讓程式碼從函式程式設計的重要層面獲益。


## <a name="mutable-variables"></a>可變變數
您可以使用 `mutable` 關鍵字指定可變更的變數。 F# 的可變變數通常應該有限制範圍，可以是類型欄位或區域值。 有限制範圍的可變變數更容易控制，同時也比較不會遭到誤改。

您可以透過與定義值相同的方式使用 `let` 關鍵字，將初始值指派給可變變數。 不過，差異在於後續可以透過 `<-` 運算子將新值指派給可變變數，如下列範例所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet602.fs)]
    
## <a name="related-topics"></a>相關主題


|標題|描述|
|-----|-----------|
|[let 繫結](../functions/let-bindings.md)|提供使用資訊`let`關鍵字來將名稱繫結至值和函式。|
|[函式](../functions/index.md)|提供 F# 函式的概觀。|

## <a name="see-also"></a>另請參閱
[Null 值](null-Values.md)

[F# 語言參考](../index.md)
