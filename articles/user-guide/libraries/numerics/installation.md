---
title: Microsoft hisse sayılıcs kitaplığı-yükleme ve doğrulama
description: Microsoft hisse biçimi kitaplığı 'nı Visual Studio 2019 veya sonraki yüklemenize eklemeyi öğrenin.
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 60ee91a552fad5becf8eda437406b6e0dfba0eb4
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276131"
---
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="b64cc-103">Numerics kitaplığı yükleme ve doğrulama</span><span class="sxs-lookup"><span data-stu-id="b64cc-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="b64cc-104">Hisse geliştirme seti, NuGet paketiyle Numerics işlevselliği için destek sağlar [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) .</span><span class="sxs-lookup"><span data-stu-id="b64cc-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="b64cc-105">**Visual Studio >= 2019:** Visual Studio 2019 veya sonraki bir sürümünü kullanıyorsanız, NuGet Paket Yöneticisi 'Ni kullanarak Numerics paketini ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b64cc-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="b64cc-106">Bunu yapmak için "NuGet Paketlerini Yönet..." seçeneğini belirleyin. Visual Studio 'daki "proje" menü öğesinden.</span><span class="sxs-lookup"><span data-stu-id="b64cc-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="b64cc-107">Araştır sekmesinden "Microsoft. hisse. Numerics" paket adını arayın</span><span class="sxs-lookup"><span data-stu-id="b64cc-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="b64cc-108">"Ön sürümü dahil et" i seçtiğinizden emin olun</span><span class="sxs-lookup"><span data-stu-id="b64cc-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="b64cc-109">Bu, karşıdan yüklenebilecek paketleri listeler.</span><span class="sxs-lookup"><span data-stu-id="b64cc-109">This will list the packages available for download.</span></span>
<span data-ttu-id="b64cc-110">"Microsoft. hisse. Numerics" üzerine gelindiğinde, sürüm numarasının sağında aşağı işaret eden bir ok görünür.</span><span class="sxs-lookup"><span data-stu-id="b64cc-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="b64cc-111">Numerics paketini yüklemek için oka tıklayın.</span><span class="sxs-lookup"><span data-stu-id="b64cc-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="b64cc-112">Daha ayrıntılı bilgi için bkz. [Paket Yöneticisi Kullanıcı Arabirimi Kılavuzu](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="b64cc-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="b64cc-113">Alternatif olarak, komut satırı arabirimi aracılığıyla, sayılıcs kitaplığını projenize eklemek için Package Manager konsolunu kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b64cc-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![Paket Yöneticisi konsolunu komut satırından kullanma](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="b64cc-115">Paket Yöneticisi konsolundan aşağıdakileri çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="b64cc-115">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="b64cc-116">Daha ayrıntılı bilgi için bkz. [Paket Yöneticisi konsol Kılavuzu](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="b64cc-116">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="b64cc-117">**Komut satırı veya Visual Studio Code:** Komut satırını kendi başına veya Visual Studio Code içinden kullanarak `dotnet` projenize NuGet paket başvurusu eklemek için komutunu kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="b64cc-117">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="b64cc-118">Yüklemenizin doğrulanması</span><span class="sxs-lookup"><span data-stu-id="b64cc-118">Verifying your installation</span></span>

<span data-ttu-id="b64cc-119">Hisse geliştirme seti 'nin geri kalanı gibi, Numerics kitaplığı mümkün olduğunca hızlı başlamanıza yardımcı olan örneklerle birlikte gelir.</span><span class="sxs-lookup"><span data-stu-id="b64cc-119">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="b64cc-120">Bu örnekleri kullanarak yüklemenizi test etmek için, [ana örnek depoyu](https://github.com/Microsoft/Quantum) kopyalayın ve ardından örneklerden birini çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="b64cc-120">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="b64cc-121">Örneği çalıştırmak için [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) :</span><span class="sxs-lookup"><span data-stu-id="b64cc-121">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
