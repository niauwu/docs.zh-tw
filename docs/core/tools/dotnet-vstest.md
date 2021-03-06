---
title: dotnet vstest 命令 - .NET Core CLI
description: dotnet vstest 命令會建置專案和其所有相依性。
author: guardrex
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: e11b193ff7a8c639078c5cf279b7fbbeab553c92
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-vstest"></a>dotnet vstest

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>名稱

`dotnet-vstest` - 從指定的檔案執行測試。

## <a name="synopsis"></a>概要

`dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]`

## <a name="description"></a>描述

`dotnet-vstest` 命令會執行 `VSTest.Console` 命令列應用程式，以執行自動化單元以及自動程式化 UI 應用程式測試。

## <a name="arguments"></a>引數

`TEST_FILE_NAMES`

從指定的組件執行測試。 以空格分隔多個測試組件名稱。

## <a name="options"></a>選項

`--Settings|/Settings:<Settings File>`

執行測試時要使用的設定。

`--Tests|/Tests:<Test Names>`

執行測試，其名稱符合所提供的值。 以逗號分隔多個值。

`--TestAdapterPath|/TestAdapterPath`

在測試回合中，從指定的路徑 (如果有的話) 使用自訂測試配接器。

`--Platform|/Platform:<Platform type>`

用於測試執行的目標平台架構。 有效值為 `x86`、`x64` 及 `ARM`。

`--Framework|/Framework:<Framework Version>`

用於測試執行的目標 .NET Framework 版本。 有效值的範例包括 `.NETFramework,Version=v4.6`、`.NETCoreApp,Version=v1.0` 等等。其他支援的值為 `Framework35`、`Framework40`、`Framework45` 和 `FrameworkCore10`。

`--Parallel|/Parallel`

以平行方式執行測試。 根據預設，電腦上所有的可用核心都可供使用。 以設定檔設定明確的核心數目。

`--TestCaseFilter|/TestCaseFilter:<Expression>`

執行符合指定之運算式的測試。 `<Expression>` 的格式為 `<property>Operator<value>[|&<Expression>]`，其中 Operator (運算子) 為 `=`、`!=` 或 `~` 其中之一。  運算子 `~` 具有「包含」語意，且適用於像是 `DisplayName` 的字串屬性。 括號 `()` 是用來分組子運算式。

`-?|--Help|/?|/Help`

印出命令的簡短說明。

`--logger|/logger:<Logger Uri/FriendlyName>`

指定測試結果的記錄器。  

* 若要將測試結果發行至 Team Foundation Server 中，使用 `TfsPublisher` 記錄器提供者：

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* 若要將結果記錄到 Visual Studio 測試結果檔案 (TRX)，使用 `trx` 記錄器提供者。 這個參數會以指定的記錄檔名稱，在測試結果目錄中建立檔案。 如果沒有提供 `LogFileName`，會建立唯一的檔案名稱以保留測試結果。

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

列出從指定之測試容器探索到的測試。

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

負責啟動目前處理序之父處理序的處理序 ID。

`--Port|/Port:<Port>`

指定通訊端連線和接收事件訊息的連接埠。

`--Diag|/Diag:<Path to log file>`

啟用測試平台的詳細資訊記錄檔。 記錄檔會寫入提供的檔案。

`args`

指定要傳遞至配接器的額外引數。 引數指定為格式 `<n>=<v>` 的名稱/值組，其中 `<n>` 是引數名稱而 `<v>` 是引數值。 使用空格來分隔多個引數。

## <a name="examples"></a>範例

以 `mytestproject.dll` 執行測試：

`dotnet vstest mytestproject.dll`

在 `mytestproject.dll` 中執行測試，以自訂名稱匯出到自訂資料夾：

`dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path`

以 `mytestproject.dll` 和 `myothertestproject.exe` 執行測試：

`dotnet vstest mytestproject.dll myothertestproject.exe`

執行 `TestMethod1` 測試：

`dotnet vstest /Tests:TestMethod1`

執行 `TestMethod1` 和 `TestMethod2` 測試：

`dotnet vstest /Tests:TestMethod1,TestMethod2`

