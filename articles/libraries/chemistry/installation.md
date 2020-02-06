---
title: Chemistry kitaplığı yükleme ve doğrulama | Microsoft Docs
description: Chemistry kitaplığı yükleme ve doğrulama
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: de13d1814821c612ed74a347dc8ffb5881063576
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036483"
---
# <a name="chemistry-library-installation-and-validation"></a><span data-ttu-id="2ec7d-103">Chemistry kitaplığı yükleme ve doğrulama</span><span class="sxs-lookup"><span data-stu-id="2ec7d-103">Chemistry Library Installation and Validation</span></span>

<span data-ttu-id="2ec7d-104">Hisse geliştirme seti, [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet paketi aracılığıyla hisse ve deneme uygulamaları için destek sağlar.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-104">The Quantum Development Kit provides support for quantum chemistry applications through the [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet package.</span></span>
<span data-ttu-id="2ec7d-105">Diğer NuGet paketlerinde olduğu gibi, bu, kimya kitaplığını projenize eklemek basittir.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-105">As with other NuGet packages, it's straightforward to add the chemistry library to your project.</span></span>

<span data-ttu-id="2ec7d-106">**Visual Studio 2019:** Visual Studio 2019 kullanıyorsanız, NuGet Paket Yöneticisi 'Ni kullanarak hisse kamistry paketleri ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-106">**Visual Studio 2019:** If you are using Visual Studio 2019, you can add the quantum chemistry packages by using the NuGet Package Manager.</span></span>
<span data-ttu-id="2ec7d-107">Paket yöneticisini açmak için, aşağıdaki ekran görüntüsünde gösterildiği gibi, kimya kitaplığını eklemek istediğiniz projeye sağ tıklayın ve "NuGet Paketlerini Yönet..." öğesini seçin.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-107">To open the Package Manager, right-click on the project you'd like to add the chemistry library to and select "Manage NuGet Packages...," as in the screenshot below.</span></span>

![](~/media/vs2017-nuget-manage-packages.png)

<span data-ttu-id="2ec7d-108">Araştır sekmesinden "Microsoft. hisse. Chemistry" paket adını arayın.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-108">From the Browse tab, search for the package name "Microsoft.Quantum.Chemistry."</span></span>

> [!NOTE]
> <span data-ttu-id="2ec7d-109">"Ön sürümü dahil et" onay ettiğinizden emin olun.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-109">Make sure to tick "Include prerelease."</span></span>

![](~/media/vs2017-nuget-package-search.png)

<span data-ttu-id="2ec7d-110">Bu, karşıdan yüklenebilecek paketleri listeler.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-110">This will list the packages available for download.</span></span>
<span data-ttu-id="2ec7d-111">Sol taraftaki bölmede "Microsoft. hisse. Chemistry" düğmesine tıklayın, sağ bölmedeki en son yayın öncesi sürümü seçin ve "Install" a tıklayın:</span><span class="sxs-lookup"><span data-stu-id="2ec7d-111">Click on the "Microsoft.Quantum.Chemistry on the left-hand pane, select the latest pre-release version on the right-hand pane, and click "Install":</span></span>

![](~/media/vs2017-nuget-select-chem.png)

<span data-ttu-id="2ec7d-112">Daha ayrıntılı bilgi için bkz. [Paket Yöneticisi Kullanıcı Arabirimi Kılavuzu](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="2ec7d-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="2ec7d-113">Alternatif olarak, bir komut satırı arabirimi ile, hisse anlıdeneme kitaplığını projenize eklemek için Package Manager konsolunu kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-113">Alternatively, you can use the Package Manager Console to add the quantum chemistry library to your project with a command line interface.</span></span>

![](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="2ec7d-114">Paket Yöneticisi konsolundan aşağıdakileri çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="2ec7d-114">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Chemistry
```

<span data-ttu-id="2ec7d-115">Daha ayrıntılı bilgi için bkz. [Paket Yöneticisi konsol Kılavuzu](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="2ec7d-115">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="2ec7d-116">**Komut satırı veya Visual Studio Code:** Komut satırını kendi başına veya Visual Studio Code içinden kullanarak projenize NuGet paket başvurusunu eklemek için `dotnet` komutunu kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="2ec7d-116">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a><span data-ttu-id="2ec7d-117">Yüklemenizin doğrulanması</span><span class="sxs-lookup"><span data-stu-id="2ec7d-117">Verifying Your Installation</span></span> 

<span data-ttu-id="2ec7d-118">Hisse daha hızlı bir şekilde çalışmaya başlamanıza yardımcı olmak için hisse, hisse geliştirme setinin geri kalanı gibi ücretçkmistry kitaplığı, tam olarak belgelenmiş birçok örnek ile birlikte gelir.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-118">Like the rest of the Quantum Development Kit, the quantum chemistry library comes with a number of fully documented samples to help you get up and running quickly.</span></span>
<span data-ttu-id="2ec7d-119">Bu örnekleri kullanarak yüklemenizi test etmek için, [ana örnekler deposunu](https://github.com/Microsoft/Quantum)kopyalayın ve ardından örneklerden birini çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-119">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum), then run one of the samples.</span></span>  <span data-ttu-id="2ec7d-120">Örneğin, [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) örneğini çalıştırmak için:</span><span class="sxs-lookup"><span data-stu-id="2ec7d-120">For example, to run the [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/chemistry/MolecularHydrogen
dotnet run
```

<span data-ttu-id="2ec7d-121">Depoyu kopyaladıktan sonra, Microsoft Visual Studio kullanarak hisse Kimya kitaplığı yüklemesini doğrulamak için:</span><span class="sxs-lookup"><span data-stu-id="2ec7d-121">To verify the installation of the quantum chemistry library using Microsoft Visual Studio after cloning the repository:</span></span>
    1. <span data-ttu-id="2ec7d-122">ChemistrySamples. sln çözümünü Chemistry klasöründe açın.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-122">Open the ChemistrySamples.sln solution in the Chemistry folder.</span></span>  
    2. <span data-ttu-id="2ec7d-123">Örnek/1 ' i seçin.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-123">Select Samples/1.</span></span> <span data-ttu-id="2ec7d-124">Başlangıç projesi olarak basit Motacules/Motacularhydrogen.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-124">Simple Molecules/MolecularHydrogen as the StartUp project.</span></span>
    3. <span data-ttu-id="2ec7d-125">F5 tuşuna basarak molesel Hydrogen Phase tahmine yönelik gösteri gösterisini çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-125">Press F5 to run the molecular Hydrogen quantum phase estimation demo.</span></span>

<span data-ttu-id="2ec7d-126">Enerji seviyelerinin değerlerini tahmin etme hakkında daha fazla bilgi için bkz. [enerji düzeyi tahminleri alma](xref:microsoft.quantum.chemistry.examples.energyestimate) .</span><span class="sxs-lookup"><span data-stu-id="2ec7d-126">See [Obtaining energy level estimates](xref:microsoft.quantum.chemistry.examples.energyestimate) for more information on estimating the values of energy levels.</span></span>   


## <a name="using-the-quantum-development-kit-with-nwchem"></a><span data-ttu-id="2ec7d-127">NWChem ile hisse geliştirme setini kullanma</span><span class="sxs-lookup"><span data-stu-id="2ec7d-127">Using the Quantum Development Kit with NWChem</span></span> ##

<span data-ttu-id="2ec7d-128">MolecularHydrogen örneği, el ile yapılandırılan molesel giriş verilerini kullanır.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-128">The MolecularHydrogen sample uses molecular input data that is manually configured.</span></span>  <span data-ttu-id="2ec7d-129">Bu küçük örnekler için çok iyi olsa da, ölçek at ölçeğinde hisse Hamiltonians, milyonlarca veya milyarlarca şart gerektirir.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-129">While this is fine for small examples, quantum chemistry at scale require Hamiltonians with millions or billions of terms.</span></span> <span data-ttu-id="2ec7d-130">Ölçeklenebilir hesaplama Kimya paketleri tarafından oluşturulan Hamiltonians, el ile içeri aktarmak için çok büyük.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-130">Such Hamiltonians, generated by scalable computational chemistry packages are too large to import by hand.</span></span> 

<span data-ttu-id="2ec7d-131">Hisse geliştirme kiti için bulunan hisse dili Mistry kitaplığı, bilgi Kuzey Ulusal laboratuvarda çevre molesel bilimcları Laboratuvarı (emsl) tarafından geliştirilen, en özellikle [**nwchem**](http://www.nwchem-sw.org/) hesaplama Kimya platformunu hesaplama Kimya paketleri ile birlikte çalışacak şekilde tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-131">The quantum chemistry library for the Quantum Development Kit is designed to work well with computational chemistry packages, most notably the [**NWChem**](http://www.nwchem-sw.org/) computational chemistry platform developed by the Environmental Molecular Sciences Laboratory (EMSL) at Pacific Northwest National Laboratory.</span></span>
<span data-ttu-id="2ec7d-132">Özellikle, `Microsoft.Quantum.Chemistry` paketi, en son NWChem sürümleri tarafından dışarı aktarma için desteklenen [Broombridge şemasında](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)temsil edilen hisse dili Mistry benzetim sorunlarının örneklerini yüklemeye yönelik araçlar sağlar.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-132">In particular, the `Microsoft.Quantum.Chemistry` package provides tools for loading instances of quantum chemistry simulation problems represented in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), also supported for export by recent versions of NWChem.</span></span>

<span data-ttu-id="2ec7d-133">Bir ile NWChem kullanarak hızlı bir şekilde çalışmaya başlayın ve aşağıdaki yöntemlerden birini öneririz:</span><span class="sxs-lookup"><span data-stu-id="2ec7d-133">To get up and running using NWChem together with the Quantum Development Kit, we suggest one of the following methods:</span></span>
- <span data-ttu-id="2ec7d-134">[Integraldata/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML)konumundaki örneklerle birlikte sağlanan mevcut Broombridge dosyalarını kullanmaya başlayın.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-134">Get started using existing Broombridge files provided with the samples at [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).</span></span>
- <span data-ttu-id="2ec7d-135">Yeni Brombridge sel giriş dosyaları oluşturmak için, NWChem için Web tabanlı bir ön uç olan [Microsoft Quantum Development Kit Için Emsl okları oluşturucusunu](https://arrows.emsl.pnnl.gov/api/qsharp_chem) kullanın.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-135">Use the [EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) which is a web-based frontend to NWChem, to generate new Broombridge-formated molecular input files.</span></span>  
- <span data-ttu-id="2ec7d-136">NWChem çalıştırmak için PNNL tarafından sunulan [Docker görüntüsünü](https://hub.docker.com/r/nwchemorg/nwchem-qc/) kullanın veya</span><span class="sxs-lookup"><span data-stu-id="2ec7d-136">Use the [Docker image](https://hub.docker.com/r/nwchemorg/nwchem-qc/) provided by PNNL to run NWChem, or</span></span>
- <span data-ttu-id="2ec7d-137">Platformunuz için [NWChem derleme](http://www.nwchem-sw.org/index.php/Compiling_NWChem) .</span><span class="sxs-lookup"><span data-stu-id="2ec7d-137">[Compile NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) for your platform.</span></span>

<span data-ttu-id="2ec7d-138">Bilgi için bkz. nwchem [ile](xref:microsoft.quantum.chemistry.examples.endtoend) nasıl yapılır? ile nasıl yapılır? ile nasıl yapılır? ile nasıl yapılır?</span><span class="sxs-lookup"><span data-stu-id="2ec7d-138">See [End-to-end with NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) for more information on how to work with NWChem to chemical models to analyze with the Quantum Developmen Kit chemistry library.</span></span>

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a><span data-ttu-id="2ec7d-139">Örneklerle sağlanan Broombridge dosyalarını kullanmaya başlama</span><span class="sxs-lookup"><span data-stu-id="2ec7d-139">Getting started using Broombridge files provided with the samples</span></span>

<span data-ttu-id="2ec7d-140">Hisse geliştirme seti örnekleri deposundaki [Integraldata/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) klasörü, Brombridge, moleule veri dosyalarını içerir.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-140">The [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) folder in the Quantum Development Kit Samples repository contains Broombridge-formated molecule data files.</span></span>  

<span data-ttu-id="2ec7d-141">Basit bir örnek olarak, Brombridge dosyalarından birinden Hamiltonian yüklemek için, [Getgatecount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) örneğini kullanın ve Fmıtonly algorigthms as kapılarının tahminlerini gerçekleştirin:</span><span class="sxs-lookup"><span data-stu-id="2ec7d-141">As a simple example, use the chemistry library sample, [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) to load the Hamiltonian from one of Broombridge files and perform gate estimates of quantum simulation algorigthms:</span></span>

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

<span data-ttu-id="2ec7d-142">Broombridge şeması tarafından temsil edilen momacules girişi hakkında daha fazla bilgi için bkz. [bir Hamiltonian dosyasını yükleme](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .</span><span class="sxs-lookup"><span data-stu-id="2ec7d-142">See [Loading a Hamiltonian from file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) for more information on how to input molecules represented by the Broombridge schema.</span></span>  

<span data-ttu-id="2ec7d-143">Kaynak tahmini hakkında daha fazla bilgi için bkz. [kaynak sayısını alma](xref:microsoft.quantum.chemistry.examples.resourcecounts) .</span><span class="sxs-lookup"><span data-stu-id="2ec7d-143">See [Obtaining resource counts](xref:microsoft.quantum.chemistry.examples.resourcecounts) for more information on resource estimation.</span></span>  

### <a name="getting-started-using-the-emsl-arrows-builder"></a><span data-ttu-id="2ec7d-144">EMSL okları oluşturucusunu kullanmaya başlama</span><span class="sxs-lookup"><span data-stu-id="2ec7d-144">Getting started using the EMSL Arrows Builder</span></span>

<span data-ttu-id="2ec7d-145">EMSL okları, hleule verileri oluşturmak için NWChem ve kimyasal hesaplama veritabanlarını kullanan bir araçtır.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-145">EMSL Arrows is a tool that uses NWChem and chemical computational databases to generate molecule data.</span></span>  <span data-ttu-id="2ec7d-146">[Microsoft Quantum Development Kit Için Emsl ok Builder](https://arrows.emsl.pnnl.gov/api/qsharp_chem) , birden çok molesel model Oluşturucu kullanarak modelinize girebilmeniz ve hisse geliştirme seti tarafından kullanılacak Broombridge veri dosyası oluşturmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-146">[EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) allows you to enter your model using multiple molecular model builders and generate the Broombridge datafile to be used by the Quantum Development Kit.</span></span>  

<span data-ttu-id="2ec7d-147">EMSL sayfasında, [' ınstuctions '] sekmesine tıklayın ve Broombridge dosyaları oluşturmak için [' basit örnekler '] yönergelerini izleyin.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-147">From the EMSL page, click on the ['Instuctions'] tab, and follow the ['Simple Examples'] instructions to generate Broombridge files.</span></span>  <span data-ttu-id="2ec7d-148">Ardından, bu motacules için hisse kaynağı tahminlerini görmek üzere [' GetGateCount '] çalıştırmayı deneyin.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-148">Then try running the ['GetGateCount'] to see the quantum resource estimates for these molecules.</span></span>

### <a name="installing-nwchem-from-source"></a><span data-ttu-id="2ec7d-149">Kaynaktan NWChem yükleme</span><span class="sxs-lookup"><span data-stu-id="2ec7d-149">Installing NWChem from Source</span></span>

<span data-ttu-id="2ec7d-150">NWChem kaynağından nasıl yükleneceğine ilişkin tam yönergeler [, PNNL tarafından sağlanır](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span><span class="sxs-lookup"><span data-stu-id="2ec7d-150">Full instructions on how to install NWChem from source [are provided by PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span></span>

> [!TIP]
> <span data-ttu-id="2ec7d-151">Windows 10 ' dan NWChem kullanmak istiyorsanız, Linux için Windows alt sistemi harika bir seçenektir.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-151">If you wish to use NWChem from Windows 10, the Windows Subsystem for Linux is a great option.</span></span>
> <span data-ttu-id="2ec7d-152">[Windows Için Ubuntu 18,04 LTS](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)'yi yükledikten sonra, en sevdiğiniz terminalden `ubuntu18.04` çalıştırın ve kaynaktan NWChem 'yi yüklemek için yukarıdaki yönergeleri izleyin.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-152">Once you have installed [Ubuntu 18.04 LTS for Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), run `ubuntu18.04` from your favorite terminal and follow the instructions above to install NWChem from source.</span></span>

<span data-ttu-id="2ec7d-153">Kaynaktan NWChem derledikten sonra, nwchem giriş kımlarından hızla Brombridge örnekleri oluşturmak için NWChem ile birlikte sunulan `yaml_driver` betiğini çalıştırabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="2ec7d-153">Once you have compiled NWChem from source, you can run the `yaml_driver` script provided with NWChem to quickly produce Broombridge instances from NWChem input decks:</span></span>

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

<span data-ttu-id="2ec7d-154">Bu komut, geçerli dizininizde Broombridge biçiminde yeni bir `input.yaml` dosyası oluşturur.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-154">This command will create a new `input.yaml` file in the Broombridge format within your current directory.</span></span>

### <a name="using-nwchem-with-docker"></a><span data-ttu-id="2ec7d-155">Docker ile NWChem kullanma</span><span class="sxs-lookup"><span data-stu-id="2ec7d-155">Using NWChem with Docker</span></span>

<span data-ttu-id="2ec7d-156">NWChem kullanımı için önceden oluşturulmuş görüntüler, [Docker Hub](https://hub.docker.com)aracılığıyla platformlar arası kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-156">Pre-built images for using NWChem are available cross-platform via [Docker Hub](https://hub.docker.com).</span></span>
<span data-ttu-id="2ec7d-157">Başlamak için platformunuzun Docker yükleme yönergelerini izleyin:</span><span class="sxs-lookup"><span data-stu-id="2ec7d-157">To get started, follow the Docker installation instructions for your platform:</span></span>

- [<span data-ttu-id="2ec7d-158">Ubuntu için Docker 'ı yükler</span><span class="sxs-lookup"><span data-stu-id="2ec7d-158">Install Docker for Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [<span data-ttu-id="2ec7d-159">MacOS için Docker 'ı yükler</span><span class="sxs-lookup"><span data-stu-id="2ec7d-159">Install Docker for macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)
- [<span data-ttu-id="2ec7d-160">Docker for Windows 10 yüklemesi</span><span class="sxs-lookup"><span data-stu-id="2ec7d-160">Install Docker for Windows 10</span></span>](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> <span data-ttu-id="2ec7d-161">Docker for Windows kullanıyorsanız, Docker daemon ile geçici dizininizi (genellikle bu `C:\` sürücüdür) içeren sürücüyü paylaşmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-161">If you are using Docker for Windows, you will need to share the drive containing your temporary directory (usually this is the `C:\` drive) with the Docker daemon.</span></span> <span data-ttu-id="2ec7d-162">Daha fazla bilgi için bkz. [Docker belgeleri](https://docs.docker.com/docker-for-windows/#shared-drives) .</span><span class="sxs-lookup"><span data-stu-id="2ec7d-162">See the [Docker documentation](https://docs.docker.com/docker-for-windows/#shared-drives) for more details.</span></span>

<span data-ttu-id="2ec7d-163">Docker yüklendikten sonra, görüntüyü çalıştırmak için hisse geliştirme seti örnekleri ile sağlanan PowerShell modülünü kullanabilir veya görüntüyü el ile çalıştırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-163">Once you have Docker installed, you can either use the PowerShell module provided with the Quantum Development Kit samples to run the image, or you can run the image manually.</span></span>
<span data-ttu-id="2ec7d-164">PowerShell kullanarak burada ayrıntılandırıyoruz. Docker görüntüsünü el ile kullanmak isterseniz, lütfen [görüntüyle birlikte sunulan belgelere](https://hub.docker.com/r/nwchemorg/nwchem-qc/)bakın.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-164">We detail using PowerShell here; if you would like to use the Docker image manually, please see the [documentation provided with the image](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span></span>

#### <a name="running-nwchem-through-powershell-core"></a><span data-ttu-id="2ec7d-165">PowerShell Core ile NWChem çalıştırma</span><span class="sxs-lookup"><span data-stu-id="2ec7d-165">Running NWChem through PowerShell Core</span></span>

<span data-ttu-id="2ec7d-166">NWChem Docker görüntüsünü hisse geliştirme seti ile birlikte kullanmak için, dosyaları NWChem içinde ve dışında kullanarak, sizin için dosya taşımayı işleyen küçük bir PowerShell modülü sağlıyoruz.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-166">To use the NWChem Docker image with the Quantum Development Kit, we provide a small PowerShell module that handles moving files in and out of NWChem for you.</span></span>
<span data-ttu-id="2ec7d-167">PowerShell Core yüklü değilse, [GitHub 'Daki PowerShell deposundan](https://github.com/PowerShell/PowerShell#get-powershell)platformlar arası indirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-167">If you don't already have PowerShell Core installed, you can download it cross-platform from the [PowerShell repository on GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="2ec7d-168">PowerShell Core Ayrıca, veri bilimi ve iş analizi iş akışlarıyla birlikte çalışabilirliği göstermek için bazı örnekler için de kullanılır.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-168">PowerShell Core is also used for some samples to demonstrate interoperability with data science and business analytics workflows.</span></span>

<span data-ttu-id="2ec7d-169">PowerShell Core yüklendikten sonra, geçerli oturumunuzda NWChem komutlarının kullanılabilir olması için `InvokeNWChem.psm1` içeri aktarın:</span><span class="sxs-lookup"><span data-stu-id="2ec7d-169">Once you have PowerShell Core installed, import `InvokeNWChem.psm1` to make NWChem commands available in your current session:</span></span>

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

<span data-ttu-id="2ec7d-170">Bu, `Convert-NWChemToBroombridge` komutunu geçerli PowerShell oturumunda kullanılabilir hale getirir.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-170">This will make the `Convert-NWChemToBroombridge` command available in your current PowerShell session.</span></span>
<span data-ttu-id="2ec7d-171">Docker 'daki gerekli görüntüleri indirmek ve bunları kullanarak NWChem giriş noktaları çalıştırıp, Kıosmbridge 'e çıktıyı yakalamak için aşağıdakileri çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="2ec7d-171">To download any needed images from Docker and use them to run NWChem input decks and capture output to Broombridge, run the following:</span></span>

```powershell
Convert-NWChemToBroombridge ./input.nw
```

<span data-ttu-id="2ec7d-172">Bu, `input.nw`NWChem ' i çalıştırarak bir Broombridge dosyası oluşturur.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-172">This will create a Broombridge file by running NWChem on `input.nw`.</span></span>
<span data-ttu-id="2ec7d-173">Varsayılan olarak, Broombridge çıktısı giriş destesi ile aynı ada ve yola sahip olur ve `.nw` uzantısı `.yaml`ile değiştirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-173">By default, the Broombridge output will have the same name and path as the input deck, with the `.nw` extension replaced by `.yaml`.</span></span>
<span data-ttu-id="2ec7d-174">Bu, `Convert-NWChemToBroombridge`için `-DestinationPath` parametresi kullanılarak geçersiz kılınabilir.</span><span class="sxs-lookup"><span data-stu-id="2ec7d-174">This can be overridden by using the `-DestinationPath` parameter to `Convert-NWChemToBroombridge`.</span></span>
<span data-ttu-id="2ec7d-175">Daha fazla bilgi, PowerShell 'in yerleşik yardım işlevleri kullanılarak elde edilebilir:</span><span class="sxs-lookup"><span data-stu-id="2ec7d-175">More information can be obtained by using PowerShell's built-in help functionality:</span></span>

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```
