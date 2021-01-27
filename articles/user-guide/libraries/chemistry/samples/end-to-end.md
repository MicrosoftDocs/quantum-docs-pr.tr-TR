---
title: Örnek NWChem hisse programı
description: Bir NWChem giriş destesi kullanarak, hisse kualem simülasyonu için geçit sayısı alma örneği üzerinden ilerleyin.
author: cgranade
ms.author: chgranad
ms.date: 10/23/2018
ms.topic: sample
uid: microsoft.quantum.chemistry.examples.endtoend
no-loc:
- Q#
- $$v
ms.openlocfilehash: e0ec7dcbdccbab5c81177a4223c71fd3f2ce57d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847770"
---
# <a name="end-to-end-with-nwchem"></a><span data-ttu-id="d09e9-103">NWChem ile uçtan uca</span><span class="sxs-lookup"><span data-stu-id="d09e9-103">End-to-end with NWChem</span></span> #

<span data-ttu-id="d09e9-104">Bu makalede, bir [Nwchem](http://www.nwchem-sw.org/index.php/Main_Page) giriş destesi 'nden başlayarak hisse Kualkem simülasyonu için geçit sayısı alma örneği hakkında yol göstereceğiz.</span><span class="sxs-lookup"><span data-stu-id="d09e9-104">In this article, you will walk through an example of getting gate counts for quantum chemistry simulation, starting from an [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) input deck.</span></span>
<span data-ttu-id="d09e9-105">Bu örneğe devam etmeden önce, [yükleme ve doğrulama kılavuzunu](xref:microsoft.quantum.chemistry.concepts.installation)Izleyerek Docker 'ı yüklediğinizden emin olun.</span><span class="sxs-lookup"><span data-stu-id="d09e9-105">Before proceeding with this example, make sure that you've installed Docker, following the [installation and validation guide](xref:microsoft.quantum.chemistry.concepts.installation).</span></span>

<span data-ttu-id="d09e9-106">Daha fazla bilgi için:</span><span class="sxs-lookup"><span data-stu-id="d09e9-106">For more information:</span></span>
- [<span data-ttu-id="d09e9-107">NWChem giriş noktaları yapısı</span><span class="sxs-lookup"><span data-stu-id="d09e9-107">Structure of NWChem input decks</span></span>](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [<span data-ttu-id="d09e9-108">Hisse geliştirme seti ile kullanım için giriş destesi komutları</span><span class="sxs-lookup"><span data-stu-id="d09e9-108">Input deck commands for use with the Quantum Development Kit</span></span>](https://github.com/nwchemgit/nwchem/tree/main/contrib/quasar)
- [<span data-ttu-id="d09e9-109">Kimya kitaplığı ve bağımlılıklarını yükleme</span><span class="sxs-lookup"><span data-stu-id="d09e9-109">Installing the chemistry library and dependencies</span></span>](xref:microsoft.quantum.chemistry.concepts.installation)
- [<span data-ttu-id="d09e9-110">Kaynak sayımı</span><span class="sxs-lookup"><span data-stu-id="d09e9-110">Resource counting</span></span>](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> <span data-ttu-id="d09e9-111">Bu örnek için Windows PowerShell Core 'un çalıştırılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="d09e9-111">This example requires Windows PowerShell Core to run.</span></span>
> <span data-ttu-id="d09e9-112">Üzerinde Windows, macOS veya Linux için PowerShell Core 'u indirin https://github.com/PowerShell/PowerShell .</span><span class="sxs-lookup"><span data-stu-id="d09e9-112">Download PowerShell Core for Windows, macOS, or Linux at https://github.com/PowerShell/PowerShell.</span></span>

## <a name="importing-required-powershell-modules"></a><span data-ttu-id="d09e9-113">Gerekli PowerShell modülleri içeri aktarılıyor</span><span class="sxs-lookup"><span data-stu-id="d09e9-113">Importing Required PowerShell Modules</span></span> ##

<span data-ttu-id="d09e9-114">Daha önce yapmadıysanız, hisse geliştirme seti ile çalışmaya yönelik örnekleri ve yardımcı programları içeren [Microsoft/hisse deposunu](https://github.com/Microsoft/Quantum)kopyalayın:</span><span class="sxs-lookup"><span data-stu-id="d09e9-114">If you haven't already done so, clone the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum), which contains samples and utilities for working with the Quantum Development Kit:</span></span>

```powershell
git clone https://github.com/Microsoft/Quantum
```

<span data-ttu-id="d09e9-115">Klonladıktan sonra `Microsoft/Quantum` `cd` `utilities/` klasöre uygulayın ve Docker ve nwchem Ile çalışmaya yönelik PowerShell modülünü içeri aktarın:</span><span class="sxs-lookup"><span data-stu-id="d09e9-115">Once you've cloned `Microsoft/Quantum`, perform `cd` into the `utilities/` folder and import the PowerShell module for working with Docker and NWChem:</span></span>

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> <span data-ttu-id="d09e9-116">Varsayılan olarak, Windows herhangi bir komut dosyası veya modülün güvenlik önlemi olarak çalıştırılmasını önler.</span><span class="sxs-lookup"><span data-stu-id="d09e9-116">By default, Windows prevents the running of any scripts or modules as a security measure.</span></span>
> <span data-ttu-id="d09e9-117">Windows 'da çalıştırmak gibi modüllere izin vermek için `Invoke-NWChem.psm1` ilkeyi değiştirmeniz gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="d09e9-117">To allow modules such as `Invoke-NWChem.psm1` to run on Windows, you may need to change the policy.</span></span>
> <span data-ttu-id="d09e9-118">Bunu yapmak için şu komutu çalıştırın `Set-ExecutionPolicy` :</span><span class="sxs-lookup"><span data-stu-id="d09e9-118">To do so, run the `Set-ExecutionPolicy` command:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> <span data-ttu-id="d09e9-119">PowerShell 'den çıktığınızda ilke döndürülür.</span><span class="sxs-lookup"><span data-stu-id="d09e9-119">The policy will revert when you exit PowerShell.</span></span>
> <span data-ttu-id="d09e9-120">İlkeyi kaydetmek istiyorsanız, için farklı bir değer kullanın `-Scope` :</span><span class="sxs-lookup"><span data-stu-id="d09e9-120">If you would like to save the policy, use a different value for `-Scope`:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

<span data-ttu-id="d09e9-121">Artık komutun kullanılabilir olması gerekir `Convert-NWChemToBroombridge` :</span><span class="sxs-lookup"><span data-stu-id="d09e9-121">You should now have the `Convert-NWChemToBroombridge` command available:</span></span>

```powershell
Get-Command -Module InvokeNWChem
```

<span data-ttu-id="d09e9-122">Daha sonra, `Get-GateCount` **Getgatecount** örneği ile birlikte gelen komutunu içeri aktaracağız.</span><span class="sxs-lookup"><span data-stu-id="d09e9-122">Next, we'll import the `Get-GateCount` command provided with the **GetGateCount** sample.</span></span>
<span data-ttu-id="d09e9-123">Tüm ayrıntılar için, [örnekle birlikte sunulan yönergelere](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/GetGateCount)bakın.</span><span class="sxs-lookup"><span data-stu-id="d09e9-123">For full details, see the [instructions provided with the sample](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/GetGateCount).</span></span>
<span data-ttu-id="d09e9-124">Ardından, `<runtime>` `win10-x64` `osx-x64` `linux-x64` işletim sisteminize bağlı olarak,, veya ile yerine şunu çalıştırın:</span><span class="sxs-lookup"><span data-stu-id="d09e9-124">Next, run the following, substituting `<runtime>` with either `win10-x64`, `osx-x64`, or `linux-x64`, depending on your operating system:</span></span>

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

<span data-ttu-id="d09e9-125">Artık komutun kullanılabilir olması gerekir `Get-GateCount` :</span><span class="sxs-lookup"><span data-stu-id="d09e9-125">You should now have the `Get-GateCount` command available:</span></span>

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a><span data-ttu-id="d09e9-126">Giriş noktaları</span><span class="sxs-lookup"><span data-stu-id="d09e9-126">Input Decks</span></span> ##

<span data-ttu-id="d09e9-127">NWChem paketi bir _giriş destesi_ adlı bir metin dosyası alır ve bu, bellek ayırma ayarları gibi diğer parametrelerle birlikte, çözülmesi gereken bir hisse anı sorununu belirtir.</span><span class="sxs-lookup"><span data-stu-id="d09e9-127">The NWChem package takes a text file called an _input deck_ which specifies a quantum chemistry problem to be solved, along with other parameters such as memory allocation settings.</span></span>
<span data-ttu-id="d09e9-128">Bu örnekte, NWChem ile birlikte gelen önceden oluşturulmuş giriş desteklerden birini kullanacağız.</span><span class="sxs-lookup"><span data-stu-id="d09e9-128">For this example, we'll use one of the pre-made input decks that comes with NWChem.</span></span>
<span data-ttu-id="d09e9-129">İlk olarak, [nwchemgit/nwchem deposunu](https://github.com/nwchemgit/nwchem)kopyalayın:</span><span class="sxs-lookup"><span data-stu-id="d09e9-129">First, clone the [nwchemgit/nwchem repository](https://github.com/nwchemgit/nwchem):</span></span>

> [!NOTE]
> <span data-ttu-id="d09e9-130">Bu çok büyük bir depo olduğundan, bağımsız değişkenini kullanarak bazı bant genişliğini ve disk alanını kaydetmek için basit bir kopya yapabiliriz `--depth 1` .</span><span class="sxs-lookup"><span data-stu-id="d09e9-130">Since this is a very large repository, we can do a shallow clone to save some bandwidth and disk space, using the `--depth 1` argument.</span></span>
> <span data-ttu-id="d09e9-131">Ancak bu isteğe bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="d09e9-131">This is optional, however.</span></span>
> <span data-ttu-id="d09e9-132">Kopyalama, olmadan sorunsuz çalışacaktır `--depth 1` .</span><span class="sxs-lookup"><span data-stu-id="d09e9-132">Cloning will work just fine without `--depth 1`.</span></span>

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

<span data-ttu-id="d09e9-133">`nwchemgit/nwchem`Depo, [ `QA/chem_library_tests` klasör](https://github.com/nwchemgit/nwchem/tree/main/QA/chem_library_tests)altında listelenen hisse kullanımı için tasarlanan çeşitli giriş noktaları ile gelir.</span><span class="sxs-lookup"><span data-stu-id="d09e9-133">The `nwchemgit/nwchem` repository comes with a variety of input decks intended for use with the Quantum Development Kit, listed under the [`QA/chem_library_tests` folder](https://github.com/nwchemgit/nwchem/tree/main/QA/chem_library_tests).</span></span>
<span data-ttu-id="d09e9-134">Bu örnekte, `H4` giriş destesi kullanacağız:</span><span class="sxs-lookup"><span data-stu-id="d09e9-134">For this example, we'll use the `H4` input deck:</span></span>

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

<span data-ttu-id="d09e9-135">Söz konusu olan moleule, bir açıda, `alpha` desteyi adında gösterildiği gibi belirli bir geometriye bağlı olan 4 Hydrogen ady sistemidir `h4_sto6g_alpha.nw` .</span><span class="sxs-lookup"><span data-stu-id="d09e9-135">The molecule in question is a system of 4 hydrogen atoms that are arranged in a certain geometry that depends on one angle, the parameter `alpha` as indicated in the name `h4_sto6g_alpha.nw` of the deck.</span></span> <span data-ttu-id="d09e9-136">H4, 1970s 'den beri hesaplama Kimya için bilinen bir [molesel kıyaslama](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) karşılaştırmasıdır.</span><span class="sxs-lookup"><span data-stu-id="d09e9-136">H4 is a known [molecular benchmark](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) for computational chemistry since the 1970s.</span></span> <span data-ttu-id="d09e9-137">Bu parametre, deste 'ın, `sto6g` özellikle de 6 Gauss tabanlı işlevlere sahip bir [temel](https://en.wikipedia.org/wiki/STO-nG_basis_sets) değer olan bir gösterimle ilgili olarak bir gösterimi uyguladığı bir gösterimidir.</span><span class="sxs-lookup"><span data-stu-id="d09e9-137">The parameter `sto6g` is indicative that the deck implements a representation with respect to a Slater-type orbital, specifically, a representation with respect to an [STO-nG basis set](https://en.wikipedia.org/wiki/STO-nG_basis_sets) with 6 Gaussian basis functions.</span></span> <span data-ttu-id="d09e9-138">Bu giriş destesi Ayrıca, nwchem Tenslı uygulama altyapısına (TCE), bu, hisse geliştirme seti ile birlikte çalışmak için gereken bilgileri oluşturmak üzere bir yol gösteren çeşitli yönergeler içerir:</span><span class="sxs-lookup"><span data-stu-id="d09e9-138">This input deck furthermore contains several instructions to the NWChem Tensor Contraction Engine (TCE) that direct NWChem to produce the information needed for interoperating with the Quantum Development Kit:</span></span>

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a><span data-ttu-id="d09e9-139">NWChem 'ten Brombridge çıkışı üretme ve kullanma</span><span class="sxs-lookup"><span data-stu-id="d09e9-139">Producing and Consuming Broombridge Output from NWChem</span></span> ##

<span data-ttu-id="d09e9-140">Artık, Brombridge belgelerini oluşturmak ve kullanmak için ihtiyacınız olan her şeye sahipsiniz.</span><span class="sxs-lookup"><span data-stu-id="d09e9-140">You now have everything you need to produce and consume Broombridge documents.</span></span>
<span data-ttu-id="d09e9-141">NWChem çalıştırmak ve giriş destesi için bir Broombridge belgesi üretmek için `h4_sto6g_0.000.nw` şunu çalıştırın `Convert-NWChemToBroombridge` :</span><span class="sxs-lookup"><span data-stu-id="d09e9-141">To run NWChem and produce a Broombridge document for the `h4_sto6g_0.000.nw` input deck, run `Convert-NWChemToBroombridge`:</span></span>

> [!NOTE]
> <span data-ttu-id="d09e9-142">Bu komutu ilk kez çalıştırdığınızda Docker `nwchemorg/nwchem-qc` görüntüyü sizin için indirir.</span><span class="sxs-lookup"><span data-stu-id="d09e9-142">The first time you run this command, Docker will download the `nwchemorg/nwchem-qc` image for you.</span></span>
> <span data-ttu-id="d09e9-143">Bu işlem, bağlantı hızınıza bağlı olarak biraz zaman alabilir ve büyük olasılıkla kahve kupa alma fırsatı sağlar.</span><span class="sxs-lookup"><span data-stu-id="d09e9-143">This may take a little while, depending on your connection speed, possibly providing an opportunity to get a cup of coffee.</span></span>

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

<span data-ttu-id="d09e9-144">Bu, ile kullanabileceğiniz bir Broombridge belgesi üretir `h4_sto6g_0.000.yaml` `Get-GateCount` :</span><span class="sxs-lookup"><span data-stu-id="d09e9-144">This will produce a Broombridge document called `h4_sto6g_0.000.yaml` that you can use with `Get-GateCount`:</span></span>

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

<span data-ttu-id="d09e9-145">Artık, çeşitli hisse simülasyon yöntemleri için T-Count, döndürmeler sayısı, CNOT Count vb. gibi kaynak tahmini içeren konsol çıktısını görmeniz gerekir:</span><span class="sxs-lookup"><span data-stu-id="d09e9-145">You should now see console output which contains resource estimation such as T-count, rotations count, CNOT count, etc. for various quantum simulation methods:</span></span>

```powershell 
IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Trotter
TCount              : 0
RotationsCount      : 92
CNOTCount           : 520
ElapsedMilliseconds : 327

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Qubitization
TCount              : 438
RotationsCount      : 516
CNOTCount           : 2150
ElapsedMilliseconds : 528

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Optimized Qubitization
TCount              : 3540
RotationsCount      : 18
CNOTCount           : 7932
ElapsedMilliseconds : 721
```

<span data-ttu-id="d09e9-146">Buradan yapılacak çok sayıda şey vardır:</span><span class="sxs-lookup"><span data-stu-id="d09e9-146">There are many things to go do from here:</span></span> 
- <span data-ttu-id="d09e9-147">Farklı ön tanımlı giriş noktaları deneyin, örneğin, içindeki parametresini değiştirerek `alpha` `h4_sto6g_alpha.nw`</span><span class="sxs-lookup"><span data-stu-id="d09e9-147">Try out different predefined input decks, e.g., by varying the parameter `alpha` in `h4_sto6g_alpha.nw`,</span></span> 
- <span data-ttu-id="d09e9-148">NWChem Decks 'i doğrudan düzenleyerek, örneğin `STO-nG` farklı n, çeşitli seçenekler için modelleri inceleyerek</span><span class="sxs-lookup"><span data-stu-id="d09e9-148">Try modifying the decks by editing the NWChem decks directly, e.g., exploring `STO-nG` models for various choices of n,</span></span> 
- <span data-ttu-id="d09e9-149">' De bulunan diğer önceden tanımlı NWChem giriş çklarını deneyin `nwchem/qa/chem_library_tests`</span><span class="sxs-lookup"><span data-stu-id="d09e9-149">Try other predefined NWChem input decks that are available at `nwchem/qa/chem_library_tests`,</span></span>
- <span data-ttu-id="d09e9-150">NWChem 'ten oluşturulan, önceden tanımlanmış bir Brombridge YAML değerlendirmeleri paketini deneyin ve [Microsoft/hisse deposu](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML)'nun bir parçası olarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="d09e9-150">Try out a suite of predefined Broombridge YAML benchmarks that were generated from NWChem and are available as part of the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML).</span></span> <span data-ttu-id="d09e9-151">Bu kıyaslamalar şunları içerir:</span><span class="sxs-lookup"><span data-stu-id="d09e9-151">These benchmarks include:</span></span> 
    - <span data-ttu-id="d09e9-152">molesel Hydrogen (H2), beryllium (be), Lityum hydride (LiH) gibi küçük molecules,</span><span class="sxs-lookup"><span data-stu-id="d09e9-152">small molecules such as molecular hydrogen (H2), Beryllium (Be), Lithium hydride (LiH),</span></span>
    - <span data-ttu-id="d09e9-153">Ozone (O3), Beta-carotene, cytosinüs gibi daha büyük molecules ve çok daha fazlası.</span><span class="sxs-lookup"><span data-stu-id="d09e9-153">larger molecules such as ozone (O3), beta-carotene, cytosine, and many more.</span></span> 
- <span data-ttu-id="d09e9-154">Microsoft Quantum Development Kit bir arabirimi sunan grafiksel ön uç [Emsl oklarını](https://arrows.emsl.pnnl.gov/api/qsharp_chem) deneyin.</span><span class="sxs-lookup"><span data-stu-id="d09e9-154">Try out the graphical front-end [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem) that features an interface to the Microsoft Quantum Development Kit.</span></span> 


## <a name="producing-broombridge-output-from-emsl-arrows"></a><span data-ttu-id="d09e9-155">EMSL oklarından Brombridge çıkışı üretme</span><span class="sxs-lookup"><span data-stu-id="d09e9-155">Producing Broombridge Output from EMSL Arrows</span></span> ##

<span data-ttu-id="d09e9-156">Web tabanlı ön uç EMSL oklarını kullanmaya başlamak için [burada](https://arrows.emsl.pnnl.gov/api/qsharp_chem)bir tarayıcıda gezinin.</span><span class="sxs-lookup"><span data-stu-id="d09e9-156">To get started with web-based front end EMSL Arrows, navigate a browser [here](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span></span> 

> [!NOTE]
> <span data-ttu-id="d09e9-157">Web tarayıcısında EMSL oklarını çalıştırmak, JavaScript 'In etkinleştirilmesini gerektirir.</span><span class="sxs-lookup"><span data-stu-id="d09e9-157">Running EMSL Arrows in a web browser requires JavaScript to be enabled.</span></span> <span data-ttu-id="d09e9-158">Tarayıcınızda JavaScript 'ı etkinleştirme hakkında daha fazla bilgi için lütfen bu [yönergelere](https://www.enable-javascript.com/) bakın.</span><span class="sxs-lookup"><span data-stu-id="d09e9-158">Please refer to these [instructions](https://www.enable-javascript.com/) on how to enable JavaScript in your browser.</span></span> 

<span data-ttu-id="d09e9-159">İlk olarak, sorgu kutusuna şöyle bir moleule girin ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span><span class="sxs-lookup"><span data-stu-id="d09e9-159">First, enter a molecule in the query box that says ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span></span> 

<span data-ttu-id="d09e9-160">"1, 3, 7-Trimethylxanthine" yerine "Caffeine" gibi, kendi collokual adına göre birçok motacules girebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d09e9-160">You can enter many molecules by their colloquial name, such as "caffeine" instead of "1,3,7-Trimethylxanthine".</span></span> 

<span data-ttu-id="d09e9-161">Sonra, görüntülenen düğmeye tıklayın ``theory{qsharp_chem}`` .</span><span class="sxs-lookup"><span data-stu-id="d09e9-161">Next, click the button that says ``theory{qsharp_chem}``.</span></span> <span data-ttu-id="d09e9-162">Bu, sorgu kutusunu, çalışmayı, Kıosmbridge YAML biçimindeki çıktıyı dışa aktarmaya söyleyen bir yönergeyle birlikte doldurur.</span><span class="sxs-lookup"><span data-stu-id="d09e9-162">This will populate the query box further with an instruction that will tell the run to export output in the Broombridge YAML format.</span></span> 

<span data-ttu-id="d09e9-163">Şimdi, saat ``Run Arrows`` .</span><span class="sxs-lookup"><span data-stu-id="d09e9-163">Now, clock on ``Run Arrows``.</span></span> <span data-ttu-id="d09e9-164">Girişin boyutuna bağlı olarak bu işlem biraz zaman alabilir.</span><span class="sxs-lookup"><span data-stu-id="d09e9-164">Depending on the size of the input, this might take a while.</span></span> <span data-ttu-id="d09e9-165">Ya da, belirli bir modelin daha önce hesaplanmış olması durumunda, yalnızca bir veritabanındaki arama miktarına göre çok daha hızlı bir şekilde yapılabilir.</span><span class="sxs-lookup"><span data-stu-id="d09e9-165">Or, in case the particular model has already been computed before, it can be done extremely fast as it will only amount to a lookup in a database.</span></span> <span data-ttu-id="d09e9-166">Her iki durumda da, girinizin belirttiği deste karşı belirli bir NWChem çalıştırması hakkında bilgi içeren yeni bir sayfaya yönlendirilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d09e9-166">In either case, you will be taken to a new page that contains a plethora of information about the particular run of NWChem against the deck specified by your input.</span></span> 

<span data-ttu-id="d09e9-167">Broombridge YAML dosyasını aşağıdaki üstbilgiyle başlayan bölümden indirip kaydedebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="d09e9-167">You can download and save the Broombridge YAML file from the section that starts with the following header:</span></span> 
```powershell
+==================================================+
||              Molecular Calculation             ||
+==================================================+

Id     = 48443

NWOutput = Link to NWChem Output (download)

Datafiles:
qsharp_chem.yaml-2018-10-23-14:37:42 (download)
...
```

<span data-ttu-id="d09e9-168">Yerel bir ``download`` kopyayı gibi benzersiz bir dosya adıyla kaydeden açık ' a tıklayın ``qsharp_chem48443.yaml`` (belirli bir ad her çalıştırma için farklı olacaktır).</span><span class="sxs-lookup"><span data-stu-id="d09e9-168">Click on ``download``, which saves a local copy with a unique file name such as ``qsharp_chem48443.yaml`` (the particular name will be different for each run).</span></span> <span data-ttu-id="d09e9-169">Daha sonra bu dosyayı yukarıdaki gibi daha fazla işleyebilirsiniz, örneğin,</span><span class="sxs-lookup"><span data-stu-id="d09e9-169">You can then further process this file as above, e.g., with</span></span> 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
<span data-ttu-id="d09e9-170">kaynak sayısını almak için.</span><span class="sxs-lookup"><span data-stu-id="d09e9-170">to get resource counts.</span></span> 

<span data-ttu-id="d09e9-171">EMSL okları başlangıç sayfasındaki sekmeden erişilebilen 3B moleule oluşturucusunun keyfini çıkarabilirsiniz ``Arrows Entry - 3D Builder`` .</span><span class="sxs-lookup"><span data-stu-id="d09e9-171">You might enjoy the 3D molecule builder that can be accessed from the ``Arrows Entry - 3D Builder`` tab on the EMSL Arrows start page.</span></span> <span data-ttu-id="d09e9-172">Gösterilen moleule 'in [Jsmol](http://wiki.jmol.org/index.php/JSmol) 3D resmine tıklanması, düzenleme yapmanıza izin verir.</span><span class="sxs-lookup"><span data-stu-id="d09e9-172">Clicking the [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D picture of the shown molecule will let you allow to edit it.</span></span> <span data-ttu-id="d09e9-173">Au 'ler etrafında hareket ettirmek için, au 'ler arasındaki uzaklıklara göre değişiklik yapmak, au 'ler eklemek/kaldırmak gibi işlemler yapabilirsiniz. Bu seçimlerin her biri için, ``theory{qsharp_chem}`` sorgu kutusuna eklendikten sonra, Brombridge YAML şemasının bir örneğini oluşturabilir ve daha sonra hisse</span><span class="sxs-lookup"><span data-stu-id="d09e9-173">You can move atoms around, drag atoms apart so that their inter-molecular distances change, add/remove atoms, etc. For each of these choices, once you added ``theory{qsharp_chem}`` in the query box, you can then generate an instance of the Broombridge YAML schema and further explore it using the Quantum Chemistry Library.</span></span> 
