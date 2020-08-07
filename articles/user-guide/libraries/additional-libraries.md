---
title: Ek Q# kitaplıkları kullanma
description: Hisse ve uygulamalarınıza ek kitaplıklar ekleme hakkında bilgi edinin Q# .
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: ef88ca765a394a7092eb0a60bf6f3615c082ef6a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869588"
---
# <a name="using-additional-no-locq-libraries"></a><span data-ttu-id="35eca-103">Ek Q# kitaplıkları kullanma</span><span class="sxs-lookup"><span data-stu-id="35eca-103">Using Additional Q# Libraries</span></span>

<span data-ttu-id="35eca-104">Hisse geliştirme seti, projelerinize eklenebilen _NuGet paketleri_ aracılığıyla alana özgü ek işlevler sağlar Q# .</span><span class="sxs-lookup"><span data-stu-id="35eca-104">The Quantum Development Kit provides additional domain-specific functionality through _NuGet packages_ that can be added to your Q# projects.</span></span>

| <span data-ttu-id="35eca-105">Q#Kitaplığı</span><span class="sxs-lookup"><span data-stu-id="35eca-105">Q# Library</span></span>  | <span data-ttu-id="35eca-106">NuGet paketi</span><span class="sxs-lookup"><span data-stu-id="35eca-106">NuGet package</span></span> | <span data-ttu-id="35eca-107">Notlar</span><span class="sxs-lookup"><span data-stu-id="35eca-107">Notes</span></span> |
|---------|---------|--------|
| [<span data-ttu-id="35eca-108">Q#Standart Kitaplık</span><span class="sxs-lookup"><span data-stu-id="35eca-108">Q# standard library</span></span>](xref:microsoft.quantum.libraries.standard.intro) | [<span data-ttu-id="35eca-109">**Microsoft. hisse. Standart**</span><span class="sxs-lookup"><span data-stu-id="35eca-109">**Microsoft.Quantum.Standard**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | <span data-ttu-id="35eca-110">Varsayılan olarak eklendi</span><span class="sxs-lookup"><span data-stu-id="35eca-110">Included by default</span></span> |
| [<span data-ttu-id="35eca-111">Kuantum kimyası kitaplığı</span><span class="sxs-lookup"><span data-stu-id="35eca-111">Quantum chemistry library</span></span>](xref:microsoft.quantum.chemistry.concepts.intro) | [<span data-ttu-id="35eca-112">**Microsoft.Quantum.Chemistry**</span><span class="sxs-lookup"><span data-stu-id="35eca-112">**Microsoft.Quantum.Chemistry**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [<span data-ttu-id="35eca-113">Kuantum sayısal kitaplığı</span><span class="sxs-lookup"><span data-stu-id="35eca-113">Quantum numerics library</span></span>](xref:microsoft.quantum.numerics.intro) | [<span data-ttu-id="35eca-114">**Microsoft. hisse. Numerics**</span><span class="sxs-lookup"><span data-stu-id="35eca-114">**Microsoft.Quantum.Numerics**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [<span data-ttu-id="35eca-115">Kuantum makine öğrenimi kitaplığı</span><span class="sxs-lookup"><span data-stu-id="35eca-115">Quantum machine learning library</span></span>](xref:microsoft.quantum.libraries.machine-learning.intro) | [<span data-ttu-id="35eca-116">**Microsoft.Quantum.MachineLearning**</span><span class="sxs-lookup"><span data-stu-id="35eca-116">**Microsoft.Quantum.MachineLearning**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

<span data-ttu-id="35eca-117">Bir hisse geliştirme setini tercih ettiğiniz ortam ve ana bilgisayar diliyle kullanılmak üzere yükledikten sonra, Q# başka bir yükleme yapmadan kitaplıkları ayrı ayrı projelere kolayca ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="35eca-117">Once you have installed the Quantum Development Kit for use with your preferred environment and host language, you can easily add libraries to individual Q# projects without any further installation.</span></span>

> [!NOTE]
> <span data-ttu-id="35eca-118">Bazı Q# Kitaplıklar Q# , programlarınızda birlikte çalışan veya ana bilgisayar uygulamalarınızla tümleştirilen ek araçlarla iyi çalışabilir.</span><span class="sxs-lookup"><span data-stu-id="35eca-118">Some Q# libraries may work well with additional tools that work alongside your Q# programs, or that integrate with your host applications.</span></span>
> <span data-ttu-id="35eca-119">Örneğin, [Kimya kitaplığı yükleme yönergeleri](xref:microsoft.quantum.chemistry.concepts.installation) , [ **Microsoft. hisse. kimya** paketinin](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) nwchem hesaplama Kimya platformuyla birlikte nasıl kullanılacağını ve `qdk-chem` hisse atıkmistry verileriyle çalışmak için komut satırı araçlarının nasıl yükleneceğini açıklamaktadır.</span><span class="sxs-lookup"><span data-stu-id="35eca-119">For example, the [chemistry library installation instructions](xref:microsoft.quantum.chemistry.concepts.installation) describe how to use the [**Microsoft.Quantum.Chemistry** package](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) together with the NWChem computational chemistry platform, and how to install the `qdk-chem` command-line tools for working with quantum chemistry data.</span></span>

## <a name="no-locq-command-line-applications-or-net-interopability"></a>[<span data-ttu-id="35eca-120">Q#komut satırı uygulamaları veya .NET karşılıklı kullanılabilirliği</span><span class="sxs-lookup"><span data-stu-id="35eca-120">Q# command-line applications or .NET interopability</span></span>](#tab/tabid-csproj)

<span data-ttu-id="35eca-121">**Komut satırı veya Visual Studio Code:** Komut satırını kendi başına veya Visual Studio Code içinden kullanarak `dotnet` projenize bir NuGet paket başvurusu eklemek için komutunu kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="35eca-121">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add a NuGet package reference to your project.</span></span>
<span data-ttu-id="35eca-122">Örneğin, [**Microsoft. hisse. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) paketini eklemek için aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="35eca-122">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

<span data-ttu-id="35eca-123">**Visual Studio:** Visual Studio 2019 veya sonraki bir sürümü kullanıyorsanız, Q# NuGet Paket Yöneticisi 'ni kullanarak ek paketler ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="35eca-123">**Visual Studio:** If you are using Visual Studio 2019 or later, you can add additional Q# packages using the NuGet Package Manager.</span></span>
<span data-ttu-id="35eca-124">Bir paket yüklemek için:</span><span class="sxs-lookup"><span data-stu-id="35eca-124">To load a package:</span></span> 
1. <span data-ttu-id="35eca-125">Visual Studio 'da açık bir proje ile, **Proje** menüsünden **NuGet Paketlerini Yönet...** öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="35eca-125">With a project open in Visual Studio, select **Manage NuGet Packages...** from the **Project** menu.</span></span>

2. <span data-ttu-id="35eca-126">**Araştır**' a tıklayın, **ön sürümü dahil et** ' i seçin ve "Microsoft. hisse. Numerics" paket adını arayın.</span><span class="sxs-lookup"><span data-stu-id="35eca-126">Click **Browse**, select **Include prerelease** and search for the package name "Microsoft.Quantum.Numerics".</span></span> <span data-ttu-id="35eca-127">Bu, karşıdan yüklenebilecek paketleri listeler.</span><span class="sxs-lookup"><span data-stu-id="35eca-127">This will list the packages available for download.</span></span>

3. <span data-ttu-id="35eca-128">**Microsoft. hisse. Numerics** ' ın üzerine gelin ve sayı, sayı eklemek için sürüm numarasının sağ tarafındaki aşağı açılan oka tıklayın.</span><span class="sxs-lookup"><span data-stu-id="35eca-128">Hover over **Microsoft.Quantum.Numerics** and click the downward-pointing arrow to the right of the version number to install the numerics package.</span></span>

<span data-ttu-id="35eca-129">Daha ayrıntılı bilgi için bkz. [Paket Yöneticisi Kullanıcı Arabirimi Kılavuzu](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="35eca-129">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="35eca-130">Alternatif olarak, komut satırı arabirimi aracılığıyla, sayılıcs kitaplığını projenize eklemek için Package Manager konsolunu kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="35eca-130">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![Paket Yöneticisi konsolunu komut satırından kullanma](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="35eca-132">Paket Yöneticisi konsolundan aşağıdakileri çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="35eca-132">From the Package Manager Console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="35eca-133">Daha ayrıntılı bilgi için bkz. [Paket Yöneticisi konsol Kılavuzu](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="35eca-133">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

## <a name="ino-locq-notebooks"></a>[<span data-ttu-id="35eca-134">I Q# Not defterleri</span><span class="sxs-lookup"><span data-stu-id="35eca-134">IQ# Notebooks</span></span>](#tab/tabid-notebook)

<span data-ttu-id="35eca-135">Q# [ `%package` MAGIC komutunu](xref:microsoft.quantum.iqsharp.magic-ref.package)kullanarak bir ı not defterinde kullanılabilecek ek paketleri kullanılabilir hale getirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="35eca-135">You can make additional packages available for use in an IQ# Notebook by using the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="35eca-136">Örneğin, bir I not defterinde kullanmak üzere [**Microsoft. hisse. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) paketini eklemek için Q# bir not defteri hücresinde aşağıdaki komutu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="35eca-136">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following command in a notebook cell:</span></span>

```
%package Microsoft.Quantum.Numerics
```

<span data-ttu-id="35eca-137">Bu komutun ardından, paket Not Defteri içindeki herhangi bir hücre için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="35eca-137">Following this command, the package is available to any cells within the notebook.</span></span>
<span data-ttu-id="35eca-138">Paketi Q# geçerli çalışma alanındaki koddan kullanılabilir hale getirmek için, paketinizi ekledikten sonra çalışma alanını yeniden yükleyin:</span><span class="sxs-lookup"><span data-stu-id="35eca-138">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```
%workspace reload
```

## <a name="python-interoperability"></a>[<span data-ttu-id="35eca-139">Python birlikte çalışabilirliği</span><span class="sxs-lookup"><span data-stu-id="35eca-139">Python interoperability</span></span>](#tab/tabid-python)


<span data-ttu-id="35eca-140">Yöntemini kullanarak, Python ana bilgisayarında kullanılabilecek ek paketleri kullanılabilir hale getirebilirsiniz [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) .</span><span class="sxs-lookup"><span data-stu-id="35eca-140">You can make additional packages available for use in a Python host program by using the [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) method.</span></span>
<span data-ttu-id="35eca-141">Örneğin, bir I not defterinde kullanmak üzere [**Microsoft. hisse. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) paketini eklemek Için Q# aşağıdaki python kodunu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="35eca-141">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following Python code:</span></span>

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

<span data-ttu-id="35eca-142">Bu komutun ardından paket kullanılarak derlenen tüm kodlar için kullanılabilir hale getirilir Q# `qsharp.compile` .</span><span class="sxs-lookup"><span data-stu-id="35eca-142">Following this command, the package will be made available to any Q# code compiled using `qsharp.compile`.</span></span>
<span data-ttu-id="35eca-143">Paketi Q# geçerli çalışma alanındaki koddan kullanılabilir hale getirmek için, paketinizi ekledikten sonra çalışma alanını yeniden yükleyin:</span><span class="sxs-lookup"><span data-stu-id="35eca-143">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```python
qsharp.reload()
```

***
