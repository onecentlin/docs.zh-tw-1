---
title: "在 DockerFile 中使用 Windows PowerShell 命令來設定 Windows 容器 (Docker 標準基礎)"
description: "Microsoft 平台和工具的容器化 Docker 應用程式生命週期"
keywords: "Docker, 微服務, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3c9a4bec4f48d988ecf8c75ff340300b83a1faef
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/23/2017
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>在 DockerFile 中使用 Windows PowerShell 命令來設定 Windows 容器 (Docker 標準基礎)

與[Windows 容器](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview)，您可以將轉換的 Docker 映像您現有的 Windows 應用程式，並將其部署在 Docker 生態系統的其他部分相同的工具。

若要使用 Windows 容器，您只需要撰寫 Windows PowerShell 命令在 DockerFile 中，如下列範例所示：

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

在此情況下，我們會使用 Windows PowerShell 來安裝 Windows Server Core 基本映像，以及 IIS。

在類似的方式，您也可以使用 Windows PowerShell 命令來設定其他元件，類似傳統的 ASP.NET 4.x 和.NET 4.6 或任何其他 Windows 軟體，如下所示：

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
[Previous] (visual-studio-tools-for-docker.md) [Next] (../docker-devops-workflow/index.md)
