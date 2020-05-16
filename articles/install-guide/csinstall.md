---
title: Q# ve .NET ile geliştirme
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 155367dbb1373f00e2b0bd732a5319b32462c9f9
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426498"
---
# <a name="develop-with-q-and-net"></a><span data-ttu-id="88366-102">Q# ve .NET ile geliştirme</span><span class="sxs-lookup"><span data-stu-id="88366-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="88366-103">Q #, C# ve F # gibi .NET dilleri ile birlikte oynamak üzere geliştirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="88366-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="88366-104">Bu kılavuzda, bir .NET dilinde yazılmış bir ana bilgisayar programıyla Q # ' ı nasıl kullanacağınızı göstereceğiz.</span><span class="sxs-lookup"><span data-stu-id="88366-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="88366-105">Önkoşullar</span><span class="sxs-lookup"><span data-stu-id="88366-105">Prerequisites</span></span>

- <span data-ttu-id="88366-106">[Q # komut satırı projeleriyle kullanılmak üzere](xref:microsoft.quantum.install.standalone)hisse geliştirme setini yükler.</span><span class="sxs-lookup"><span data-stu-id="88366-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="88366-107">Bir Q # kitaplığı ve bir .NET Konağı oluşturma</span><span class="sxs-lookup"><span data-stu-id="88366-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="88366-108">İlk adım, Q # kitaplığınız için projeler oluşturmaktır ve Q # kitaplığınızda tanımlanan işlemler ve işlevlere çağrı yapılacak .NET ana bilgisayarı için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="88366-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="88366-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="88366-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="88366-110">Yeni bir Q # kitaplığı oluşturun</span><span class="sxs-lookup"><span data-stu-id="88366-110">Create a new Q# library</span></span>
  - <span data-ttu-id="88366-111">**Dosya**  ->  **Yeni**  ->  **Proje** 'ye git</span><span class="sxs-lookup"><span data-stu-id="88366-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="88366-112">Arama kutusuna "Q #" yazın</span><span class="sxs-lookup"><span data-stu-id="88366-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="88366-113">**Q # kitaplığı** Seç</span><span class="sxs-lookup"><span data-stu-id="88366-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="88366-114">**İleri** Seç</span><span class="sxs-lookup"><span data-stu-id="88366-114">Select **Next**</span></span>
  - <span data-ttu-id="88366-115">Kitaplığınız için bir ad ve konum seçin</span><span class="sxs-lookup"><span data-stu-id="88366-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="88366-116">"Projeyi ve çözümü aynı dizinde yerleştir" **işaretinin işaretli** olmadığından emin olun</span><span class="sxs-lookup"><span data-stu-id="88366-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="88366-117">**Oluştur** ' u seçin</span><span class="sxs-lookup"><span data-stu-id="88366-117">Select **Create**</span></span>
- <span data-ttu-id="88366-118">Yeni bir C# veya F # ana bilgisayar programı oluşturma</span><span class="sxs-lookup"><span data-stu-id="88366-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="88366-119">**Dosya** → **Yeni** → **projesine** git</span><span class="sxs-lookup"><span data-stu-id="88366-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="88366-120">C# veya F için "konsol uygulaması (.NET Core") "seçeneğini belirleyin #</span><span class="sxs-lookup"><span data-stu-id="88366-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="88366-121">**İleri** Seç</span><span class="sxs-lookup"><span data-stu-id="88366-121">Select **Next**</span></span>
  - <span data-ttu-id="88366-122">*Çözüm*altında "çözüme Ekle" yi seçin</span><span class="sxs-lookup"><span data-stu-id="88366-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="88366-123">Ana bilgisayar programınız için bir ad seçin</span><span class="sxs-lookup"><span data-stu-id="88366-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="88366-124">**Oluştur** ' u seçin</span><span class="sxs-lookup"><span data-stu-id="88366-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="88366-125">Visual Studio Code veya komut satırı</span><span class="sxs-lookup"><span data-stu-id="88366-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="88366-126">Yeni bir Q # kitaplığı oluşturun</span><span class="sxs-lookup"><span data-stu-id="88366-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="88366-127">Yeni bir C# veya F # konsol projesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="88366-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="88366-128">Q # kitaplığınızı ana bilgisayar programınızdaki bir başvuru olarak ekleyin</span><span class="sxs-lookup"><span data-stu-id="88366-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="88366-129">Seçim Her iki proje için bir çözüm oluşturun</span><span class="sxs-lookup"><span data-stu-id="88366-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="88366-130">.NET 'ten Q # içine çağırma</span><span class="sxs-lookup"><span data-stu-id="88366-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="88366-131">Projelerinizi yukarıdaki yönergeleri izleyerek ayarladıktan sonra, .NET konsol uygulamanızdan Q # dosyasına çağrı yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="88366-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="88366-132">Q # derleyicisi her bir Q # işlemi ve bir Benzetici üzerinde hisse</span><span class="sxs-lookup"><span data-stu-id="88366-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="88366-133">Örneğin, [.net birlikte çalışabilirlik örneği](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) aşağıdaki bir Q # işlemi örneğini içerir:</span><span class="sxs-lookup"><span data-stu-id="88366-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="88366-134">Bu işlemi bir hisse Benzetici üzerinde .NET 'ten çağırmak için, `Run` `RunAlgorithm` Q # derleyicisi tarafından oluşturulan .net sınıfının yöntemini kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="88366-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="88366-135">C#</span><span class="sxs-lookup"><span data-stu-id="88366-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="88366-136">F#</span><span class="sxs-lookup"><span data-stu-id="88366-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="88366-137">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="88366-137">Next steps</span></span>

<span data-ttu-id="88366-138">Hem Q # komut satırı programlarında hem de .NET ile birlikte çalışabilirliğine sahip olduğunuza göre, [ilk hisse programınızı](xref:microsoft.quantum.quickstarts.qrng)yazabilir ve çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="88366-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
