---
title: 使用 dotnet vstest 測試已發行的輸出
description: 了解如何使用 dotnet vstest 命令在已發行的輸出上執行測試。
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 2f750a8bb0907069691c4a4491beeb4b1733df29
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2018
---
# <a name="test-published-output-with-dotnet-vstest"></a>使用 dotnet vstest 測試已發行的輸出

您可以使用 `dotnet vstest` 命令在已經發行的輸出上執行測試。 此作法適用於 xUnit、MSTest 和 NUnit 測試。 只需找到已發行輸出之一部分的 DLL 檔，並執行：

```
dotnet vstest <MyPublishedTests>.dll
```

其中 `<MyPublishedTests>` 是已發行測試專案的名稱。

## <a name="example-of-running-tests-on-a-published-dll"></a>在已發行的 DLL 上執行測試的範例

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> 注意：如果您的應用程式是以 `netcoreapp` 以外的架構為目標，您仍然能以架構旗標傳入目標架構，來執行 `dotnet vstest` 命令。 例如，`dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`。 在 Visual Studio 2017 Update 5 中，系統會自動偵測所需架構。

## <a name="see-also"></a>另請參閱
 [使用 dotnet test 及 xUnit 執行單元測試](unit-testing-with-dotnet-test.md)  
 [使用 dotnet test 及 MSTest 執行單元測試](unit-testing-with-mstest.md)  
