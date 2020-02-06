---
title: Numerics kitaplığı yükleme ve doğrulama | Microsoft Docs
description: Numerics kitaplığı yükleme ve doğrulama
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: c41bb73ea484271689eea2ca1b59ce6639dc15a7
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036466"
---
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="a8d97-103">Numerics kitaplığı yükleme ve doğrulama</span><span class="sxs-lookup"><span data-stu-id="a8d97-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="a8d97-104">Hisse geliştirme seti, [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet paketiyle Numerics işlevselliği için destek sağlar.</span><span class="sxs-lookup"><span data-stu-id="a8d97-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="a8d97-105">**Visual Studio > = 2019:** Visual Studio 2019 veya sonraki bir sürümünü kullanıyorsanız, NuGet Paket Yöneticisi 'Ni kullanarak Numerics paketini ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a8d97-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="a8d97-106">Bunu yapmak için "NuGet Paketlerini Yönet..." seçeneğini belirleyin. Visual Studio 'daki "proje" menü öğesinden.</span><span class="sxs-lookup"><span data-stu-id="a8d97-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="a8d97-107">Araştır sekmesinden "Microsoft. hisse. Numerics" paket adını arayın</span><span class="sxs-lookup"><span data-stu-id="a8d97-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="a8d97-108">"Ön sürümü dahil et" i seçtiğinizden emin olun</span><span class="sxs-lookup"><span data-stu-id="a8d97-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="a8d97-109">Bu, karşıdan yüklenebilecek paketleri listeler.</span><span class="sxs-lookup"><span data-stu-id="a8d97-109">This will list the packages available for download.</span></span>
<span data-ttu-id="a8d97-110">"Microsoft. hisse. Numerics" üzerine gelindiğinde, sürüm numarasının sağında aşağı işaret eden bir ok görünür.</span><span class="sxs-lookup"><span data-stu-id="a8d97-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="a8d97-111">Numerics paketini yüklemek için oka tıklayın.</span><span class="sxs-lookup"><span data-stu-id="a8d97-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="a8d97-112">Daha ayrıntılı bilgi için bkz. [Paket Yöneticisi Kullanıcı Arabirimi Kılavuzu](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="a8d97-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="a8d97-113">Alternatif olarak, komut satırı arabirimi aracılığıyla, sayılıcs kitaplığını projenize eklemek için Package Manager konsolunu kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a8d97-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![](../../media/vs2017-nuget-console-menu.png)

<span data-ttu-id="a8d97-114">Paket Yöneticisi konsolundan aşağıdakileri çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="a8d97-114">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="a8d97-115">Daha ayrıntılı bilgi için bkz. [Paket Yöneticisi konsol Kılavuzu](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="a8d97-115">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="a8d97-116">**Komut satırı veya Visual Studio Code:** Komut satırını kendi başına veya Visual Studio Code içinden kullanarak projenize NuGet paket başvurusunu eklemek için `dotnet` komutunu kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="a8d97-116">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="a8d97-117">Yüklemenizin doğrulanması</span><span class="sxs-lookup"><span data-stu-id="a8d97-117">Verifying your installation</span></span>

<span data-ttu-id="a8d97-118">Hisse geliştirme seti 'nin geri kalanı gibi, Numerics kitaplığı mümkün olduğunca hızlı başlamanıza yardımcı olan örneklerle birlikte gelir.</span><span class="sxs-lookup"><span data-stu-id="a8d97-118">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="a8d97-119">Bu örnekleri kullanarak yüklemenizi test etmek için, [ana örnek depoyu](https://github.com/Microsoft/Quantum) kopyalayın ve ardından örneklerden birini çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="a8d97-119">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="a8d97-120">[`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) örneğini çalıştırmak için:</span><span class="sxs-lookup"><span data-stu-id="a8d97-120">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
