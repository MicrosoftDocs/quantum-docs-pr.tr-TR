---
title: Q# ve .NET ile geliştirme
description: .NET dillerini kullanarak Q# uygulaması oluşturmayı öğrenin.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: de79c361331766572f5608c341be766e071e01b5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844302"
---
# <a name="develop-with-no-locq-and-net"></a><span data-ttu-id="540be-103">Q# ve .NET ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="540be-103">Develop with Q# and .NET</span></span>

<span data-ttu-id="540be-104">Q# dili, C# ve F# gibi .NET dilleri ile birlikte uyumlu olacak şekilde tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="540be-104">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="540be-105">Bu kılavuzda, Q# dilinin bir .NET dilinde yazılmış konak programıyla nasıl kullanılacağını gösteriyoruz.</span><span class="sxs-lookup"><span data-stu-id="540be-105">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="540be-106">İlk olarak Q# uygulamasını ve .NET konağını oluşturuyoruz, sonra da konaktan Q# diline nasıl çağrı yapılacağını gösteriyoruz.</span><span class="sxs-lookup"><span data-stu-id="540be-106">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="540be-107">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="540be-107">Prerequisites</span></span>

- <span data-ttu-id="540be-108">[Q# projeleriyle birlikte kullanmak için](xref:microsoft.quantum.install.standalone) Quantum geliştirme setini yükleyin.</span><span class="sxs-lookup"><span data-stu-id="540be-108">Install the Quantum Development Kit [for use with Q# projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-no-locq-library-and-a-net-host"></a><span data-ttu-id="540be-109">Q# kitaplığı ve .NET konağı oluşturma</span><span class="sxs-lookup"><span data-stu-id="540be-109">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="540be-110">İlk adım, Q# kitaplığınız ve Q# kitaplığınızda tanımlanan işlemlere ve işlevlere çağrı yapacak .NET konağı için projeler oluşturmaktır.</span><span class="sxs-lookup"><span data-stu-id="540be-110">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="540be-111">Geliştirme ortamınıza karşılık gelen sekmedeki yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="540be-111">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="540be-112">Visual Studio veya VS Code dışında bir düzenleyici kullanıyorsanız komut istemi adımlarını izlemeniz yeterlidir.</span><span class="sxs-lookup"><span data-stu-id="540be-112">If you are using an editor other than Visual Studio or VS Code, simply follow the command prompt steps.</span></span>

### <a name="visual-studio-code-or-command-prompt"></a>[<span data-ttu-id="540be-113">Visual Studio Code veya komut istemi</span><span class="sxs-lookup"><span data-stu-id="540be-113">Visual Studio Code or command prompt</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="540be-114">Yeni bir Q# kitaplığı oluşturun</span><span class="sxs-lookup"><span data-stu-id="540be-114">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="540be-115">Yeni bir C# veya F# konsol projesi oluşturun</span><span class="sxs-lookup"><span data-stu-id="540be-115">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="540be-116">Q# kitaplığınızı konak programınızdaki bir başvuru olarak ekleyin</span><span class="sxs-lookup"><span data-stu-id="540be-116">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="540be-117">[İsteğe Bağlı] Her iki proje için bir çözüm oluşturun</span><span class="sxs-lookup"><span data-stu-id="540be-117">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="540be-118">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="540be-118">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="540be-119">Yeni bir Q# kitaplığı oluşturun</span><span class="sxs-lookup"><span data-stu-id="540be-119">Create a new Q# library</span></span>
  - <span data-ttu-id="540be-120">**Dosya** -> **Yeni** -> **Proje**’ye gidin</span><span class="sxs-lookup"><span data-stu-id="540be-120">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="540be-121">Arama kutusuna "Q#" yazın</span><span class="sxs-lookup"><span data-stu-id="540be-121">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="540be-122">**Q# Kitaplığı**’nı seçin</span><span class="sxs-lookup"><span data-stu-id="540be-122">Select **Q# Library**</span></span>
  - <span data-ttu-id="540be-123">**İleri**’yi seçin</span><span class="sxs-lookup"><span data-stu-id="540be-123">Select **Next**</span></span>
  - <span data-ttu-id="540be-124">Kitaplığınız için bir ad ve konum seçin</span><span class="sxs-lookup"><span data-stu-id="540be-124">Choose a name and location for your library</span></span>
  - <span data-ttu-id="540be-125">"Projeyi ve çözümü aynı dizine yerleştir" seçeneğinin **işaretlenmemiş** olduğundan emin olun</span><span class="sxs-lookup"><span data-stu-id="540be-125">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="540be-126">**Oluştur**’u seçin</span><span class="sxs-lookup"><span data-stu-id="540be-126">Select **Create**</span></span>
- <span data-ttu-id="540be-127">Yeni bir C# veya F# konak programı oluşturun</span><span class="sxs-lookup"><span data-stu-id="540be-127">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="540be-128">**Dosya** → **Yeni** → **Proje**’ye gidin</span><span class="sxs-lookup"><span data-stu-id="540be-128">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="540be-129">C# veya F# için "Konsol Uygulaması (.NET Core")" seçeneğini belirleyin</span><span class="sxs-lookup"><span data-stu-id="540be-129">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="540be-130">**İleri**’yi seçin</span><span class="sxs-lookup"><span data-stu-id="540be-130">Select **Next**</span></span>
  - <span data-ttu-id="540be-131">*Çözüm* altında "çözüme ekle"yi seçin</span><span class="sxs-lookup"><span data-stu-id="540be-131">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="540be-132">Konak programınız için bir ad seçin</span><span class="sxs-lookup"><span data-stu-id="540be-132">Choose a name for your host program</span></span>
  - <span data-ttu-id="540be-133">**Oluştur**’u seçin</span><span class="sxs-lookup"><span data-stu-id="540be-133">Select **Create**</span></span>

<span data-ttu-id="540be-134">\*\*_</span><span class="sxs-lookup"><span data-stu-id="540be-134">\*\*_</span></span>

## <a name="calling-into-no-locq-from-net"></a><span data-ttu-id="540be-135">.NET'ten Q# diline çağrı yapma</span><span class="sxs-lookup"><span data-stu-id="540be-135">Calling into Q# from .NET</span></span>

<span data-ttu-id="540be-136">Projelerinizi yukarıdaki yönergeleri izleyerek ayarladıktan sonra, .NET konsol uygulamanızdan Q# diline çağrı yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="540be-136">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="540be-137">Q# derleyicisi, her Q# işlemi ve işlevi için kuantum programlarınızı bir simülatörde çalıştırmanızı sağlayan .NET sınıfları oluşturur.</span><span class="sxs-lookup"><span data-stu-id="540be-137">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="540be-138">Örneğin, [.NET birlikte çalışabilirlik örneği](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet), aşağıdaki Q# işlemi örneğini içerir:</span><span class="sxs-lookup"><span data-stu-id="540be-138">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="540be-139">Bu işlemi bir kuantum simülatöründe .NET'ten çağırmak için, Q# derleyicisi tarafından oluşturulan `RunAlgorithm` .NET sınıfının `Run` metodunu kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="540be-139">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="540be-140">C#</span><span class="sxs-lookup"><span data-stu-id="540be-140">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="540be-141">F#</span><span class="sxs-lookup"><span data-stu-id="540be-141">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

<span data-ttu-id="540be-142">_\*\*</span><span class="sxs-lookup"><span data-stu-id="540be-142">_\*\*</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="540be-143">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="540be-143">Next steps</span></span>

<span data-ttu-id="540be-144">Artık hem Q# uygulamaları hem de .NET ile birlikte çalışabilirlik için Quantum geliştirme setini ayarladığınıza göre, [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="540be-144">Now that you have the Quantum Development Kit set up for both Q# applications and interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
