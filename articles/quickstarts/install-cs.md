---
title: Q# ve .NET ile geliştirme
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 2b0b16bdd9fccc3b668036e6df2b20e11b32f8b6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274157"
---
# <a name="develop-with-q-and-net"></a><span data-ttu-id="78997-102">Q# ve .NET ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="78997-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="78997-103">Q# dili, C# ve F# gibi .NET dilleri ile birlikte uyumlu olacak şekilde tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="78997-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="78997-104">Bu kılavuzda, Q# dilinin bir .NET dilinde yazılmış konak programıyla nasıl kullanılacağını göstereceğiz.</span><span class="sxs-lookup"><span data-stu-id="78997-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="78997-105">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="78997-105">Prerequisites</span></span>

- <span data-ttu-id="78997-106">[Q# komut satırı projeleriyle birlikte kullanmak için](xref:microsoft.quantum.install.standalone) Quantum geliştirme setini yükleyin.</span><span class="sxs-lookup"><span data-stu-id="78997-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="78997-107">Q# kitaplığı ve .NET konağı oluşturma</span><span class="sxs-lookup"><span data-stu-id="78997-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="78997-108">İlk adım, Q# kitaplığınız ve Q# kitaplığınızda tanımlanan işlemlere ve işlevlere çağrı yapacak .NET konağı için projeleri oluşturmaktır.</span><span class="sxs-lookup"><span data-stu-id="78997-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="78997-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="78997-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="78997-110">Yeni bir Q# kitaplığı oluşturun</span><span class="sxs-lookup"><span data-stu-id="78997-110">Create a new Q# library</span></span>
  - <span data-ttu-id="78997-111">**Dosya** -> **Yeni** -> **Proje**’ye gidin</span><span class="sxs-lookup"><span data-stu-id="78997-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="78997-112">Arama kutusuna "Q#" yazın</span><span class="sxs-lookup"><span data-stu-id="78997-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="78997-113">**Q# Kitaplığı**’nı seçin</span><span class="sxs-lookup"><span data-stu-id="78997-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="78997-114">**İleri**’yi seçin</span><span class="sxs-lookup"><span data-stu-id="78997-114">Select **Next**</span></span>
  - <span data-ttu-id="78997-115">Kitaplığınız için bir ad ve konum seçin</span><span class="sxs-lookup"><span data-stu-id="78997-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="78997-116">"Projeyi ve çözümü aynı dizine yerleştir" seçeneğinin **işaretlenmemiş** olduğundan emin olun</span><span class="sxs-lookup"><span data-stu-id="78997-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="78997-117">**Oluştur**’u seçin</span><span class="sxs-lookup"><span data-stu-id="78997-117">Select **Create**</span></span>
- <span data-ttu-id="78997-118">Yeni bir C# veya F# konak programı oluşturun</span><span class="sxs-lookup"><span data-stu-id="78997-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="78997-119">**Dosya** → **Yeni** → **Proje**’ye gidin</span><span class="sxs-lookup"><span data-stu-id="78997-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="78997-120">C# veya F# için "Konsol Uygulaması (.NET Core")" seçeneğini belirleyin</span><span class="sxs-lookup"><span data-stu-id="78997-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="78997-121">**İleri**’yi seçin</span><span class="sxs-lookup"><span data-stu-id="78997-121">Select **Next**</span></span>
  - <span data-ttu-id="78997-122">*Çözüm* altında "çözüme ekle"yi seçin</span><span class="sxs-lookup"><span data-stu-id="78997-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="78997-123">Konak programınız için bir ad seçin</span><span class="sxs-lookup"><span data-stu-id="78997-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="78997-124">**Oluştur**’u seçin</span><span class="sxs-lookup"><span data-stu-id="78997-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="78997-125">Visual Studio Code veya Komut Satırı</span><span class="sxs-lookup"><span data-stu-id="78997-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="78997-126">Yeni bir Q# kitaplığı oluşturun</span><span class="sxs-lookup"><span data-stu-id="78997-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="78997-127">Yeni bir C# veya F# konsol projesi oluşturun</span><span class="sxs-lookup"><span data-stu-id="78997-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="78997-128">Q# kitaplığınızı konak programınızdaki bir başvuru olarak ekleyin</span><span class="sxs-lookup"><span data-stu-id="78997-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="78997-129">[İsteğe Bağlı] Her iki proje için bir çözüm oluşturun</span><span class="sxs-lookup"><span data-stu-id="78997-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="78997-130">.NET'ten Q# diline çağrı yapma</span><span class="sxs-lookup"><span data-stu-id="78997-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="78997-131">Projelerinizi yukarıdaki yönergeleri izleyerek ayarladıktan sonra, .NET konsol uygulamanızdan Q# diline çağrı yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="78997-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="78997-132">Q# derleyicisi, her Q# işlemi ve işlevi için kuantum programlarınızı bir simülatörde çalıştırmanızı sağlayan .NET sınıfları oluşturur.</span><span class="sxs-lookup"><span data-stu-id="78997-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="78997-133">Örneğin, [.NET birlikte çalışabilirlik örneği](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet), aşağıdaki Q# işlemi örneğini içerir:</span><span class="sxs-lookup"><span data-stu-id="78997-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="78997-134">Bu işlemi bir kuantum simülatöründe .NET'ten çağırmak için, Q# derleyicisi tarafından oluşturulan `RunAlgorithm` .NET sınıfının `Run` metodunu kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="78997-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="78997-135">C#</span><span class="sxs-lookup"><span data-stu-id="78997-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="78997-136">F#</span><span class="sxs-lookup"><span data-stu-id="78997-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="78997-137">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="78997-137">Next steps</span></span>

<span data-ttu-id="78997-138">Artık hem Q# komut satırı programları hem de .NET ile birlikte çalışabilirlik için Quantum geliştirme setini ayarladığınıza göre, [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="78997-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
