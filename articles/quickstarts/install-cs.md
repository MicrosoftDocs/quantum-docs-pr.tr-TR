---
title: Q# ve .NET ile geliştirme
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 714c15d9589095f0fe395fcd6941672167879dca
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885496"
---
# <a name="develop-with-q-and-net"></a><span data-ttu-id="7e303-102">Q# ve .NET ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="7e303-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="7e303-103">Q# dili, C# ve F# gibi .NET dilleri ile birlikte uyumlu olacak şekilde tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="7e303-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="7e303-104">Bu kılavuzda, Q# dilinin bir .NET dilinde yazılmış konak programıyla nasıl kullanılacağını gösteriyoruz.</span><span class="sxs-lookup"><span data-stu-id="7e303-104">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="7e303-105">İlk olarak Q# uygulamasını ve .NET konağını oluşturuyoruz, sonra da konaktan Q# diline nasıl çağrı yapılacağını gösteriyoruz.</span><span class="sxs-lookup"><span data-stu-id="7e303-105">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7e303-106">Ön koşullar</span><span class="sxs-lookup"><span data-stu-id="7e303-106">Prerequisites</span></span>

- <span data-ttu-id="7e303-107">[Q# komut satırı projeleriyle birlikte kullanmak için](xref:microsoft.quantum.install.standalone) Quantum geliştirme setini yükleyin.</span><span class="sxs-lookup"><span data-stu-id="7e303-107">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="7e303-108">Q# kitaplığı ve .NET konağı oluşturma</span><span class="sxs-lookup"><span data-stu-id="7e303-108">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="7e303-109">İlk adım, Q# kitaplığınız ve Q# kitaplığınızda tanımlanan işlemlere ve işlevlere çağrı yapacak .NET konağı için projeleri oluşturmaktır.</span><span class="sxs-lookup"><span data-stu-id="7e303-109">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="7e303-110">Geliştirme ortamınıza karşılık gelen sekmedeki yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="7e303-110">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="7e303-111">Visual Studio veya VS Code dışında bir düzenleyici kullanıyorsanız komut satırı adımlarını izlemeniz yeterlidir.</span><span class="sxs-lookup"><span data-stu-id="7e303-111">If you are using an editor other than Visual Studio or VS Code, simply follow the command line steps.</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="7e303-112">Visual Studio Code veya Komut Satırı</span><span class="sxs-lookup"><span data-stu-id="7e303-112">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="7e303-113">Yeni bir Q# kitaplığı oluşturun</span><span class="sxs-lookup"><span data-stu-id="7e303-113">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="7e303-114">Yeni bir C# veya F# konsol projesi oluşturun</span><span class="sxs-lookup"><span data-stu-id="7e303-114">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="7e303-115">Q# kitaplığınızı konak programınızdaki bir başvuru olarak ekleyin</span><span class="sxs-lookup"><span data-stu-id="7e303-115">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="7e303-116">[İsteğe Bağlı] Her iki proje için bir çözüm oluşturun</span><span class="sxs-lookup"><span data-stu-id="7e303-116">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="7e303-117">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="7e303-117">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="7e303-118">Yeni bir Q# kitaplığı oluşturun</span><span class="sxs-lookup"><span data-stu-id="7e303-118">Create a new Q# library</span></span>
  - <span data-ttu-id="7e303-119">**Dosya** -> **Yeni** -> **Proje**’ye gidin</span><span class="sxs-lookup"><span data-stu-id="7e303-119">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="7e303-120">Arama kutusuna "Q#" yazın</span><span class="sxs-lookup"><span data-stu-id="7e303-120">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="7e303-121">**Q# Kitaplığı**’nı seçin</span><span class="sxs-lookup"><span data-stu-id="7e303-121">Select **Q# Library**</span></span>
  - <span data-ttu-id="7e303-122">**İleri**’yi seçin</span><span class="sxs-lookup"><span data-stu-id="7e303-122">Select **Next**</span></span>
  - <span data-ttu-id="7e303-123">Kitaplığınız için bir ad ve konum seçin</span><span class="sxs-lookup"><span data-stu-id="7e303-123">Choose a name and location for your library</span></span>
  - <span data-ttu-id="7e303-124">"Projeyi ve çözümü aynı dizine yerleştir" seçeneğinin **işaretlenmemiş** olduğundan emin olun</span><span class="sxs-lookup"><span data-stu-id="7e303-124">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="7e303-125">**Oluştur**’u seçin</span><span class="sxs-lookup"><span data-stu-id="7e303-125">Select **Create**</span></span>
- <span data-ttu-id="7e303-126">Yeni bir C# veya F# konak programı oluşturun</span><span class="sxs-lookup"><span data-stu-id="7e303-126">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="7e303-127">**Dosya** → **Yeni** → **Proje**’ye gidin</span><span class="sxs-lookup"><span data-stu-id="7e303-127">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="7e303-128">C# veya F# için "Konsol Uygulaması (.NET Core")" seçeneğini belirleyin</span><span class="sxs-lookup"><span data-stu-id="7e303-128">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="7e303-129">**İleri**’yi seçin</span><span class="sxs-lookup"><span data-stu-id="7e303-129">Select **Next**</span></span>
  - <span data-ttu-id="7e303-130">*Çözüm* altında "çözüme ekle"yi seçin</span><span class="sxs-lookup"><span data-stu-id="7e303-130">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="7e303-131">Konak programınız için bir ad seçin</span><span class="sxs-lookup"><span data-stu-id="7e303-131">Choose a name for your host program</span></span>
  - <span data-ttu-id="7e303-132">**Oluştur**’u seçin</span><span class="sxs-lookup"><span data-stu-id="7e303-132">Select **Create**</span></span>

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="7e303-133">.NET'ten Q# diline çağrı yapma</span><span class="sxs-lookup"><span data-stu-id="7e303-133">Calling into Q# from .NET</span></span>

<span data-ttu-id="7e303-134">Projelerinizi yukarıdaki yönergeleri izleyerek ayarladıktan sonra, .NET konsol uygulamanızdan Q# diline çağrı yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7e303-134">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="7e303-135">Q# derleyicisi, her Q# işlemi ve işlevi için kuantum programlarınızı bir simülatörde çalıştırmanızı sağlayan .NET sınıfları oluşturur.</span><span class="sxs-lookup"><span data-stu-id="7e303-135">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="7e303-136">Örneğin, [.NET birlikte çalışabilirlik örneği](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet), aşağıdaki Q# işlemi örneğini içerir:</span><span class="sxs-lookup"><span data-stu-id="7e303-136">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="7e303-137">Bu işlemi bir kuantum simülatöründe .NET'ten çağırmak için, Q# derleyicisi tarafından oluşturulan `RunAlgorithm` .NET sınıfının `Run` metodunu kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="7e303-137">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="7e303-138">C#</span><span class="sxs-lookup"><span data-stu-id="7e303-138">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="7e303-139">F#</span><span class="sxs-lookup"><span data-stu-id="7e303-139">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="7e303-140">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="7e303-140">Next steps</span></span>

<span data-ttu-id="7e303-141">Artık hem Q# komut satırı programları hem de .NET ile birlikte çalışabilirlik için Quantum geliştirme setini ayarladığınıza göre, [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7e303-141">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
