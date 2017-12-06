---
title: "現代化 web 應用程式的特性"
description: "使用 ASP.NET Core 和 Azure 的現代化 Web 應用程式架構設計人員 |現代化 web 應用程式的特性"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 9ff9380b318457a842dec4e41b9b74dcddcda3d3
ms.sourcegitcommit: 882e02b086d7cb9c75f748494cf7a8d3377c5874
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2017
---
# <a name="characteristics-of-modern-web-applications"></a><span data-ttu-id="25c70-103">現代化 Web 應用程式的特性</span><span class="sxs-lookup"><span data-stu-id="25c70-103">Characteristics of Modern Web Applications</span></span>

> <span data-ttu-id="25c70-104">"…</span><span class="sxs-lookup"><span data-stu-id="25c70-104">"…</span></span> <span data-ttu-id="25c70-105">使用適當的設計功能廉價地有。</span><span class="sxs-lookup"><span data-stu-id="25c70-105">with proper design, the features come cheaply.</span></span> <span data-ttu-id="25c70-106">這種方法是棘手，但會繼續成功 」。</span><span class="sxs-lookup"><span data-stu-id="25c70-106">This approach is arduous, but continues to succeed."</span></span>  
> <span data-ttu-id="25c70-107">_\-Dennis Ritchie_</span><span class="sxs-lookup"><span data-stu-id="25c70-107">_\- Dennis Ritchie_</span></span>

## <a name="summary"></a><span data-ttu-id="25c70-108">總結</span><span class="sxs-lookup"><span data-stu-id="25c70-108">Summary</span></span>

<span data-ttu-id="25c70-109">現代化 web 應用程式有較高使用者期望和比以往更高的要求。</span><span class="sxs-lookup"><span data-stu-id="25c70-109">Modern web applications have higher user expectations and greater demands than ever before.</span></span> <span data-ttu-id="25c70-110">現今的 web 應用程式應該要使用 24/7 從任何地方在世界中，並可從幾乎任何裝置或螢幕大小。</span><span class="sxs-lookup"><span data-stu-id="25c70-110">Today's web apps are expected to be available 24/7 from anywhere in the world, and usable from virtually any device or screen size.</span></span> <span data-ttu-id="25c70-111">Web 應用程式必須是安全、 彈性且可調整以符合尖峰需求。</span><span class="sxs-lookup"><span data-stu-id="25c70-111">Web applications must be secure, flexible, and scalable to meet spikes in demand.</span></span> <span data-ttu-id="25c70-112">現在越來越複雜的案例中處理的方式使用 JavaScript，並有效率地透過 web 應用程式開發介面進行通訊的用戶端上建置豐富的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="25c70-112">Increasingly, complex scenarios should be handled by rich user experiences built on the client using JavaScript, and communicating efficiently through web APIs.</span></span>

<span data-ttu-id="25c70-113">ASP.NET Core 最適合用於現代化 web 應用程式和以雲端為基礎的託管案例。</span><span class="sxs-lookup"><span data-stu-id="25c70-113">ASP.NET Core is optimized for modern web applications and cloud-based hosting scenarios.</span></span> <span data-ttu-id="25c70-114">它的模組化設計可讓應用程式實際使用，改善應用程式的安全性和效能，同時降低裝載的資源需求的功能而定。</span><span class="sxs-lookup"><span data-stu-id="25c70-114">Its modular design enables applications to depend on only those features they actually use, improving application security and performance while reducing hosting resource requirements.</span></span>

## <a name="reference-application-eshoponweb"></a><span data-ttu-id="25c70-115">參考應用程式： eShopOnWeb</span><span class="sxs-lookup"><span data-stu-id="25c70-115">Reference Application: eShopOnWeb</span></span>

<span data-ttu-id="25c70-116">本指南包含參考應用程式， *eShopOnWeb*，示範一些原則與建議。</span><span class="sxs-lookup"><span data-stu-id="25c70-116">This guidance includes a reference application, *eShopOnWeb*, that demonstrates some of the principles and recommendations.</span></span> <span data-ttu-id="25c70-117">應用程式是簡單的線上存放區可支援瀏覽的上衣、 咖啡馬克及其他行銷目的目錄。</span><span class="sxs-lookup"><span data-stu-id="25c70-117">The application is a simple online store which supports browsing through a catalog of shirts, coffee mugs, and other marketing items.</span></span> <span data-ttu-id="25c70-118">參考應用程式是故意簡單化以使其更容易了解。</span><span class="sxs-lookup"><span data-stu-id="25c70-118">The reference application is deliberately simple in order to make it easy to understand.</span></span>

<span data-ttu-id="25c70-119">**圖 2-1。**</span><span class="sxs-lookup"><span data-stu-id="25c70-119">**Figure 2-1.**</span></span> <span data-ttu-id="25c70-120">eShopOnWeb</span><span class="sxs-lookup"><span data-stu-id="25c70-120">eShopOnWeb</span></span>

![](./media/image2-1.png)

> ### <a name="reference-application"></a><span data-ttu-id="25c70-121">參考應用程式</span><span class="sxs-lookup"><span data-stu-id="25c70-121">Reference Application</span></span>
> - <span data-ttu-id="25c70-122">**eShopOnWeb**</span><span class="sxs-lookup"><span data-stu-id="25c70-122">**eShopOnWeb**</span></span>  
> <span data-ttu-id="25c70-123"><https://github.com/dotnet/eShopOnWeb></span><span class="sxs-lookup"><span data-stu-id="25c70-123"><https://github.com/dotnet/eShopOnWeb></span></span>

## <a name="cloud-hosted-and-scalable"></a><span data-ttu-id="25c70-124">雲端裝載及擴充</span><span class="sxs-lookup"><span data-stu-id="25c70-124">Cloud-Hosted and Scalable</span></span>

<span data-ttu-id="25c70-125">ASP.NET Core 最適合雲端 （公用雲端、 私人雲端、 任何雲端），因為它是低記憶體及高輸送量。</span><span class="sxs-lookup"><span data-stu-id="25c70-125">ASP.NET Core is optimized for the cloud (public cloud, private cloud, any cloud) because it is low-memory and high-throughput.</span></span> <span data-ttu-id="25c70-126">ASP.NET Core 應用程式的較小的足跡表示您可以主控多個相同的硬體上，而且當使用付款-做為您的雲端代管服務支付較少的資源。</span><span class="sxs-lookup"><span data-stu-id="25c70-126">The smaller footprint of ASP.NET Core applications means you can host more of them on the same hardware, and you pay for fewer resources when using pay-as-you go cloud hosting services.</span></span> <span data-ttu-id="25c70-127">高輸送量表示您可以做進一步降低需要投資在伺服器與裝載基礎結構中從指定的相同硬體的應用程式更多的客戶。</span><span class="sxs-lookup"><span data-stu-id="25c70-127">The higher-throughput means you can serve more customers from an application given the same hardware, further reducing the need to invest in servers and hosting infrastructure.</span></span>

## <a name="cross-platform"></a><span data-ttu-id="25c70-128">跨平台</span><span class="sxs-lookup"><span data-stu-id="25c70-128">Cross Platform</span></span>

<span data-ttu-id="25c70-129">ASP.NET Core 是跨平台，並可以在 Linux 和 MacOS，以及 Windows 上執行。</span><span class="sxs-lookup"><span data-stu-id="25c70-129">ASP.NET Core is cross-platform, and can run on Linux and MacOS as well as Windows.</span></span> <span data-ttu-id="25c70-130">這會開啟許多新的開發和部署的應用程式以 ASP.NET Core 建置選項。</span><span class="sxs-lookup"><span data-stu-id="25c70-130">This opens up many new options for both development and deployment of apps built with ASP.NET Core.</span></span> <span data-ttu-id="25c70-131">Docker 容器，通常今天執行 Linux，可以主控 ASP.NET Core 應用程式，讓他們可以運用的優點[容器和 microservices](../microservices-architecture)。</span><span class="sxs-lookup"><span data-stu-id="25c70-131">Docker containers, which typically run Linux today, can host ASP.NET Core applications, allowing them to take advantage of the benefits of [containers and microservices](../microservices-architecture).</span></span>

## <a name="modular-and-loosely-coupled"></a><span data-ttu-id="25c70-132">模組化且鬆散偶合</span><span class="sxs-lookup"><span data-stu-id="25c70-132">Modular and Loosely Coupled</span></span>

<span data-ttu-id="25c70-133">NuGet 封裝會在.NET Core 的首要和 ASP.NET Core 應用程式以透過 NuGet 許多程式庫所組成。</span><span class="sxs-lookup"><span data-stu-id="25c70-133">NuGet packages are first-class citizens in .NET Core, and ASP.NET Core apps are composed of many libraries through NuGet.</span></span> <span data-ttu-id="25c70-134">此資料粒度的功能可協助確保應用程式只取決於和部署它們實際所需的功能，減少其耗用量和安全性弱點介面區。</span><span class="sxs-lookup"><span data-stu-id="25c70-134">This granularity of functionality helps ensure apps only depend on and deploy functionality they actually require, reducing their footprint and security vulnerability surface area.</span></span>

<span data-ttu-id="25c70-135">ASP.NET Core 也完全支援相依性插入內部和應用程式層級。</span><span class="sxs-lookup"><span data-stu-id="25c70-135">ASP.NET Core also fully supports dependency injection, both internally and at the application level.</span></span> <span data-ttu-id="25c70-136">介面可以擁有多個可以視需要空出的實作。</span><span class="sxs-lookup"><span data-stu-id="25c70-136">Interfaces can have multiple implementations that can be swapped out as needed.</span></span> <span data-ttu-id="25c70-137">相依性插入允許鬆散結合這些介面，讓它們更容易擴充、 維護及測試應用程式。</span><span class="sxs-lookup"><span data-stu-id="25c70-137">Dependency injection allows apps to loosely couple to those interfaces, making them easier to extend, maintain, and test.</span></span>

## <a name="easily-tested-with-automated-tests"></a><span data-ttu-id="25c70-138">輕鬆地測試自動化測試</span><span class="sxs-lookup"><span data-stu-id="25c70-138">Easily Tested with Automated Tests</span></span>

<span data-ttu-id="25c70-139">ASP.NET Core 應用程式支援單元測試，和其鬆散偶合和相依性資料隱碼攻擊的支援方便交換基礎結構顧慮假的實作，基於測試目的。</span><span class="sxs-lookup"><span data-stu-id="25c70-139">ASP.NET Core applications support unit testing, and their loose coupling and support for dependency injections makes it easy to swap infrastructure concerns with fake implementations for test purposes.</span></span> <span data-ttu-id="25c70-140">ASP.NET Core 也提供了可用於在記憶體中的主機應用程式 TestServer。</span><span class="sxs-lookup"><span data-stu-id="25c70-140">ASP.NET Core also ships a TestServer that can be used to host apps in memory.</span></span> <span data-ttu-id="25c70-141">功能測試然後可以對此記憶體中伺服器上，執行完整的應用程式堆疊 （包含中介軟體、 路由、 模型繫結、 篩選等） 提出要求並接收回應時，在大部分的時間花費裝載在實際伺服器上的應用程式以透過網路層級的要求。</span><span class="sxs-lookup"><span data-stu-id="25c70-141">Functional tests can then make requests to this in-memory server, exercising the full application stack (including middleware, routing, model binding, filters, etc.) and receiving a response, all in a fraction of the time it would take to host the app on a real server and make requests through the network layer.</span></span> <span data-ttu-id="25c70-142">這些測試特別容易撰寫，而重要的應用程式開發介面是越來越重要現代化 web 應用程式中。</span><span class="sxs-lookup"><span data-stu-id="25c70-142">These tests are especially easy to write, and valuable, for APIs, which are increasingly important in modern web applications.</span></span>

## <a name="traditional-and-spa-behaviors-supported"></a><span data-ttu-id="25c70-143">傳統和支援 SPA 行為</span><span class="sxs-lookup"><span data-stu-id="25c70-143">Traditional and SPA Behaviors Supported</span></span>

<span data-ttu-id="25c70-144">傳統 web 應用程式有很少用戶端行為，但已改為依賴瀏覽、 查詢和應用程式可能需要進行的更新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="25c70-144">Traditional web applications have involved little client-side behavior, but instead have relied on the server for all navigation, queries, and updates the app might need to make.</span></span> <span data-ttu-id="25c70-145">每個新使用者進行的作業會轉譯成新的 web 要求，正在重新載入完整的頁面，在終端使用者的瀏覽器中的結果。</span><span class="sxs-lookup"><span data-stu-id="25c70-145">Each new operation made by the user would be translated into a new web request, with the result being a full page reload in the end user's browser.</span></span> <span data-ttu-id="25c70-146">傳統的模型檢視控制器 (MVC) 架構通常會遵循這種方式，與每個新的要求對應至不同的控制器動作，而後者會使用模型和傳回的檢視。</span><span class="sxs-lookup"><span data-stu-id="25c70-146">Classic Model-View-Controller (MVC) frameworks typically follow this approach, with each new request corresponding to a different controller action, which in turn would work with a model and return a view.</span></span> <span data-ttu-id="25c70-147">指定的頁面中的某些個別作業可能會增強 AJAX （非同步 JavaScript 和 XML） 功能，但整體架構的應用程式使用許多不同的 MVC 檢視和 URL 端點。</span><span class="sxs-lookup"><span data-stu-id="25c70-147">Some individual operations on a given page might be enhanced with AJAX (Asynchronous JavaScript and XML) functionality, but the overall architecture of the app used many different MVC views and URL endpoints.</span></span>

<span data-ttu-id="25c70-148">單一頁面應用程式 (SPAs)，相較之下，涉及極少數的動態產生的伺服器端頁面載入 （如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="25c70-148">Single Page Applications (SPAs), by contrast, involve very few dynamically generated server-side page loads (if any).</span></span> <span data-ttu-id="25c70-149">許多 SPAs 是靜態的 HTML 檔案載入必要的 JavaScript 程式庫，以啟動並執行應用程式內初始化。</span><span class="sxs-lookup"><span data-stu-id="25c70-149">Many SPAs are initialized within a static HTML file which loads the necessary JavaScript libraries to start and run the app.</span></span> <span data-ttu-id="25c70-150">這些應用程式進行的 web 應用程式開發介面，其滿足資料要求，使用量，而且可以提供更豐富的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="25c70-150">These apps make heavy usage of web APIs for their data needs, and can provide much richer user experiences.</span></span>

<span data-ttu-id="25c70-151">許多 web 應用程式牽涉到傳統 web 應用程式行為 （通常用於內容） 和 SPAs （適用於互動功能） 的組合。</span><span class="sxs-lookup"><span data-stu-id="25c70-151">Many web applications involve a combination of traditional web application behavior (typically for content) and SPAs (for interactivity).</span></span> <span data-ttu-id="25c70-152">ASP.NET Core 支援 MVC 和 web 應用程式開發介面中相同的應用程式使用同一組工具和基礎架構程式庫。</span><span class="sxs-lookup"><span data-stu-id="25c70-152">ASP.NET Core supports both MVC and web APIs in the same application, using the same set of tools and underlying framework libraries.</span></span>

## <a name="simple-development-and-deployment"></a><span data-ttu-id="25c70-153">簡單開發和部署</span><span class="sxs-lookup"><span data-stu-id="25c70-153">Simple Development and Deployment</span></span>

<span data-ttu-id="25c70-154">ASP.NET Core 應用程式可以使用簡單的文字編輯器與命令列介面或完整的開發環境，例如 Visual Studio 來撰寫。</span><span class="sxs-lookup"><span data-stu-id="25c70-154">ASP.NET Core applications can be written using simple text editors and command line interfaces, or full-featured development environments like Visual Studio.</span></span> <span data-ttu-id="25c70-155">整合應用程式通常會部署到單一的端點。</span><span class="sxs-lookup"><span data-stu-id="25c70-155">Monolithic applications are typically deployed to a single endpoint.</span></span> <span data-ttu-id="25c70-156">可以輕鬆地自動化部署，以持續整合 (CI) 和持續傳遞 (CD) 管線的過程中發生。</span><span class="sxs-lookup"><span data-stu-id="25c70-156">Deployments can easily be automated to occur as part of a continuous integration (CI) and continuous delivery (CD) pipeline.</span></span> <span data-ttu-id="25c70-157">除了傳統的 CI/CD 工具，Windows Azure 擁有其整合式 git 儲存機制的支援和自動部署更新，因為它們會對指定的 git 分支或標記。</span><span class="sxs-lookup"><span data-stu-id="25c70-157">In addition to traditional CI/CD tools, Windows Azure has integrated support for git repositories and can automatically deploy updates as they are made to a specified git branch or tag.</span></span>

## <a name="traditional-aspnet-and-web-forms"></a><span data-ttu-id="25c70-158">傳統的 ASP.NET 和 Web Form</span><span class="sxs-lookup"><span data-stu-id="25c70-158">Traditional ASP.NET and Web Forms</span></span>

<span data-ttu-id="25c70-159">除了 ASP.NET Core，傳統 ASP.NET 4.x 仍然是穩定且可靠的平台，建置 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="25c70-159">In addition to ASP.NET Core, traditional ASP.NET 4.x continues to be a robust and reliable platform for building web applications.</span></span> <span data-ttu-id="25c70-160">ASP.NET 支援 MVC 和 Web API 的開發模型，以及 Web Form，這非常適合用來開發豐富的網頁應用程式和功能豐富的協力廠商元件生態系統。</span><span class="sxs-lookup"><span data-stu-id="25c70-160">ASP.NET supports MVC and Web API development models, as well as Web Forms, which is well-suited to rich page-based application development and features a rich third-party component ecosystem.</span></span> <span data-ttu-id="25c70-161">Windows Azure 絕佳傳統 ASP.NET 4.x 應用程式，支援與許多開發人員熟悉此平台。</span><span class="sxs-lookup"><span data-stu-id="25c70-161">Windows Azure has great longstanding support for ASP.NET 4.x applications, and many developers are familiar with this platform.</span></span>

> ### <a name="references--modern-web-applications"></a><span data-ttu-id="25c70-162">參考 – 現代化 Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="25c70-162">References – Modern Web Applications</span></span>
> - <span data-ttu-id="25c70-163">**ASP.NET Core 簡介**</span><span class="sxs-lookup"><span data-stu-id="25c70-163">**Introduction to ASP.NET Core**</span></span>  
> <span data-ttu-id="25c70-164"><https://docs.microsoft.com/aspnet/core/></span><span class="sxs-lookup"><span data-stu-id="25c70-164"><https://docs.microsoft.com/aspnet/core/></span></span>
> - <span data-ttu-id="25c70-165">**六個索引鍵優點的 ASP.NET Core 使不同且更好的**</span><span class="sxs-lookup"><span data-stu-id="25c70-165">**Six Key Benefits of ASP.NET Core which make it Different and Better**</span></span>  
> <span data-ttu-id="25c70-166"><https://blog.trigent.com/six-key-benefits-of-asp-net-core-1-0-which-make-it-different-better/></span><span class="sxs-lookup"><span data-stu-id="25c70-166"><https://blog.trigent.com/six-key-benefits-of-asp-net-core-1-0-which-make-it-different-better/></span></span>
> - <span data-ttu-id="25c70-167">**在 ASP.NET Core 中測試**</span><span class="sxs-lookup"><span data-stu-id="25c70-167">**Testing in ASP.NET Core**</span></span>  
> <span data-ttu-id="25c70-168"><https://docs.microsoft.com/aspnet/core/testing/></span><span class="sxs-lookup"><span data-stu-id="25c70-168"><https://docs.microsoft.com/aspnet/core/testing/></span></span>

>[!div class="step-by-step"]
<span data-ttu-id="25c70-169">[上一個](index.md) [下一步] (choose-between-traditional-web-and-single-page-apps.md)</span><span class="sxs-lookup"><span data-stu-id="25c70-169">[Previous] (index.md) [Next] (choose-between-traditional-web-and-single-page-apps.md)</span></span>