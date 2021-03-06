---
title: 例外狀況類型 (F#)
description: '了解如何定義和使用 F # 例外狀況類型。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 6aaa5cd1b94f829b98d5aed5dcf6e30472a8b751
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2018
---
# <a name="exception-types"></a>例外狀況類型

有兩種類別的 F # 中的例外狀況：.NET 例外狀況型別和 F # 例外狀況類型。 本主題描述如何定義和使用 F # 例外狀況類型。


## <a name="syntax"></a>語法

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>備註
在先前的語法，*例外狀況型別*是新的 F # 例外狀況類型、 名稱和*引數型別*表示引發此類型的例外狀況時，可以提供的引數的類型。 您可以指定多個引數的元組型別，利用*引數型別*。

F # 例外狀況的一般定義如下。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

您可以使用來產生此類型的例外狀況`raise`函數，如下所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

您可以直接在中的篩選條件中使用的 F # 例外狀況類型`try...with`運算式，如下列範例所示。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

您定義的例外狀況類型`exception`F # 中的關鍵字是新的類型繼承自`System.Exception`。


## <a name="see-also"></a>另請參閱
[例外狀況處理](index.md)

[例外狀況：`raise` 函式](the-raise-function.md)

[例外狀況階層架構](https://msdn.microsoft.com/library/z4c5tckx.aspx)
