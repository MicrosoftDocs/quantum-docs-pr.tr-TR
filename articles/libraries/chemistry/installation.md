---
title: Chemistry kitaplığı yükleme ve doğrulama | Microsoft Docs
description: Chemistry kitaplığı yükleme ve doğrulama
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: fd43c783fa82c7219e143a57759919606fdd197f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184211"
---
# <a name="chemistry-library-installation-and-validation"></a>Chemistry kitaplığı yükleme ve doğrulama

Hisse geliştirme seti, [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet paketi aracılığıyla hisse ve deneme uygulamaları için destek sağlar.
Diğer NuGet paketlerinde olduğu gibi, bu, kimya kitaplığını projenize eklemek basittir.

**Visual Studio 2019:** Visual Studio 2019 kullanıyorsanız, NuGet Paket Yöneticisi 'Ni kullanarak hisse kamistry paketleri ekleyebilirsiniz.
Paket yöneticisini açmak için, aşağıdaki ekran görüntüsünde gösterildiği gibi, kimya kitaplığını eklemek istediğiniz projeye sağ tıklayın ve "NuGet Paketlerini Yönet..." öğesini seçin.

![](~/media/vs2017-nuget-manage-packages.png)

Araştır sekmesinden "Microsoft. hisse. Chemistry" paket adını arayın.

> [!NOTE]
> "Ön sürümü dahil et" onay ettiğinizden emin olun.

![](~/media/vs2017-nuget-package-search.png)

Bu, karşıdan yüklenebilecek paketleri listeler.
Sol taraftaki bölmede "Microsoft. hisse. Chemistry" düğmesine tıklayın, sağ bölmedeki en son yayın öncesi sürümü seçin ve "Install" a tıklayın:

![](~/media/vs2017-nuget-select-chem.png)

Daha ayrıntılı bilgi için bkz. [Paket Yöneticisi Kullanıcı Arabirimi Kılavuzu](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Alternatif olarak, bir komut satırı arabirimi ile, hisse anlıdeneme kitaplığını projenize eklemek için Package Manager konsolunu kullanabilirsiniz.

![](~/media/vs2017-nuget-console-menu.png)

Paket Yöneticisi konsolundan aşağıdakileri çalıştırın:

```
Install-Package Microsoft.Quantum.Chemistry
```

Daha ayrıntılı bilgi için bkz. [Paket Yöneticisi konsol Kılavuzu](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Komut satırı veya Visual Studio Code:** Komut satırını kendi başına veya Visual Studio Code içinden kullanarak projenize NuGet paket başvurusunu eklemek için `dotnet` komutunu kullanabilirsiniz:

```bash
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a>Yüklemenizin doğrulanması 

Hisse daha hızlı bir şekilde çalışmaya başlamanıza yardımcı olmak için hisse, hisse geliştirme setinin geri kalanı gibi ücretçkmistry kitaplığı, tam olarak belgelenmiş birçok örnek ile birlikte gelir.
Bu örnekleri kullanarak yüklemenizi test etmek için, [ana örnekler deposunu](https://github.com/Microsoft/Quantum)kopyalayın ve ardından örneklerden birini çalıştırın.  Örneğin, [`MolecularHydrogen`](https://github.com/Microsoft/Quantum/tree/master/Chemistry/MolecularHydrogen) örneğini çalıştırmak için:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Chemistry/MolecularHydrogen
dotnet run
```

Depoyu kopyaladıktan sonra, Microsoft Visual Studio kullanarak hisse Kimya kitaplığı yüklemesini doğrulamak için:
    1. ChemistrySamples. sln çözümünü Chemistry klasöründe açın.  
    2. Örnek/1 ' i seçin. Başlangıç projesi olarak basit Motacules/Motacularhydrogen.
    3. F5 tuşuna basarak molesel Hydrogen Phase tahmine yönelik gösteri gösterisini çalıştırın.

Enerji seviyelerinin değerlerini tahmin etme hakkında daha fazla bilgi için bkz. [enerji düzeyi tahminleri alma](xref:microsoft.quantum.chemistry.examples.energyestimate) .   


## <a name="using-the-quantum-development-kit-with-nwchem"></a>NWChem ile hisse geliştirme setini kullanma ##

MolecularHydrogen örneği, el ile yapılandırılan molesel giriş verilerini kullanır.  Bu küçük örnekler için çok iyi olsa da, ölçek at ölçeğinde hisse Hamiltonians, milyonlarca veya milyarlarca şart gerektirir. Ölçeklenebilir hesaplama Kimya paketleri tarafından oluşturulan Hamiltonians, el ile içeri aktarmak için çok büyük. 

Hisse geliştirme kiti için bulunan hisse dili Mistry kitaplığı, hesaplama Kimya paketleri ile birlikte çalışarak, özellikle de çevresel molesel Bilimleri Laboratuvarı tarafından geliştirilen [**nwchem**](http://www.nwchem-sw.org/) hesaplama Kimya platformu ( EMSL), Kuzey Batı Ulusal Laboratuvarı.
Özellikle, `Microsoft.Quantum.Chemistry` paketi, en son NWChem sürümleri tarafından dışarı aktarma için desteklenen [Broombridge şemasında](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)temsil edilen hisse dili Mistry benzetim sorunlarının örneklerini yüklemeye yönelik araçlar sağlar.

Bir ile NWChem kullanarak hızlı bir şekilde çalışmaya başlayın ve aşağıdaki yöntemlerden birini öneririz:
- [Integraldata/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)konumundaki örneklerle birlikte sağlanan mevcut Broombridge dosyalarını kullanmaya başlayın.
- Yeni Brombridge sel giriş dosyaları oluşturmak için, NWChem için Web tabanlı bir ön uç olan [Microsoft Quantum Development Kit Için Emsl okları oluşturucusunu](https://arrows.emsl.pnnl.gov/api/qsharp_chem) kullanın.  
- NWChem çalıştırmak için PNNL tarafından sunulan [Docker görüntüsünü](https://hub.docker.com/r/nwchemorg/nwchem-qc/) kullanın veya
- Platformunuz için [NWChem derleme](http://www.nwchem-sw.org/index.php/Compiling_NWChem) .

Bilgi için bkz. nwchem [ile](xref:microsoft.quantum.chemistry.examples.endtoend) nasıl yapılır? ile nasıl yapılır? ile nasıl yapılır? ile nasıl yapılır?

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>Örneklerle sağlanan Broombridge dosyalarını kullanmaya başlama
Hisse geliştirme seti örnekleri deposundaki [Integraldata/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML) klasörü, Brombridge, moleule veri dosyalarını içerir.  

Basit bir örnek olarak, Brombridge dosyalarından birinden Hamiltonian yüklemek için, [Getgatecount](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount) örneğini kullanın ve Fmıtonly algorigthms as kapılarının tahminlerini gerçekleştirin:

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

Broombridge şeması tarafından temsil edilen momacules girişi hakkında daha fazla bilgi için bkz. [bir Hamiltonian dosyasını yükleme](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .  

Kaynak tahmini hakkında daha fazla bilgi için bkz. [kaynak sayısını alma](xref:microsoft.quantum.chemistry.examples.resourcecounts) .  

### <a name="getting-started-using-the-emsl-arrows-builder"></a>EMSL okları oluşturucusunu kullanmaya başlama

EMSL okları, hleule verileri oluşturmak için NWChem ve kimyasal hesaplama veritabanlarını kullanan bir araçtır.  [Microsoft Quantum Development Kit Için Emsl ok Builder](https://arrows.emsl.pnnl.gov/api/qsharp_chem) , birden çok molesel model Oluşturucu kullanarak modelinize girebilmeniz ve hisse geliştirme seti tarafından kullanılacak Broombridge veri dosyası oluşturmanıza olanak sağlar.  

EMSL sayfasında, [' ınstuctions '] sekmesine tıklayın ve Broombridge dosyaları oluşturmak için [' basit örnekler '] yönergelerini izleyin.  Ardından, bu motacules için hisse kaynağı tahminlerini görmek üzere [' GetGateCount '] çalıştırmayı deneyin.

### <a name="installing-nwchem-from-source"></a>Kaynaktan NWChem yükleme

NWChem kaynağından nasıl yükleneceğine ilişkin tam yönergeler [, PNNL tarafından sağlanır](http://www.nwchem-sw.org/index.php/Compiling_NWChem).

> [!TIP]
> Windows 10 ' dan NWChem kullanmak istiyorsanız, Linux için Windows alt sistemi harika bir seçenektir.
> [Windows Için Ubuntu 18,04 LTS](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)'yi yükledikten sonra, en sevdiğiniz terminalden `ubuntu18.04` çalıştırın ve kaynaktan NWChem 'yi yüklemek için yukarıdaki yönergeleri izleyin.

Kaynaktan NWChem derledikten sonra, nwchem giriş kımlarından hızla Brombridge örnekleri oluşturmak için NWChem ile birlikte sunulan `yaml_driver` betiğini çalıştırabilirsiniz:

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

Bu komut, geçerli dizininizde Broombridge biçiminde yeni bir `input.yaml` dosyası oluşturur.

### <a name="using-nwchem-with-docker"></a>Docker ile NWChem kullanma

NWChem kullanımı için önceden oluşturulmuş görüntüler, [Docker Hub](https://hub.docker.com)aracılığıyla platformlar arası kullanılabilir.
Başlamak için platformunuzun Docker yükleme yönergelerini izleyin:

- [Ubuntu için Docker 'ı yükler](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [MacOS için Docker 'ı yükler](https://docs.docker.com/docker-for-mac/install/)
- [Docker for Windows 10 yüklemesi](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> Docker for Windows kullanıyorsanız, Docker daemon ile geçici dizininizi (genellikle bu `C:\` sürücüdür) içeren sürücüyü paylaşmanız gerekir. Daha fazla bilgi için bkz. [Docker belgeleri](https://docs.docker.com/docker-for-windows/#shared-drives) .

Docker yüklendikten sonra, görüntüyü çalıştırmak için hisse geliştirme seti örnekleri ile sağlanan PowerShell modülünü kullanabilir veya görüntüyü el ile çalıştırabilirsiniz.
PowerShell kullanarak burada ayrıntılandırıyoruz. Docker görüntüsünü el ile kullanmak isterseniz, lütfen [görüntüyle birlikte sunulan belgelere](https://hub.docker.com/r/nwchemorg/nwchem-qc/)bakın.

#### <a name="running-nwchem-through-powershell-core"></a>PowerShell Core ile NWChem çalıştırma

NWChem Docker görüntüsünü hisse geliştirme seti ile birlikte kullanmak için, dosyaları NWChem içinde ve dışında kullanarak, sizin için dosya taşımayı işleyen küçük bir PowerShell modülü sağlıyoruz.
PowerShell Core yüklü değilse, [GitHub 'Daki PowerShell deposundan](https://github.com/PowerShell/PowerShell#get-powershell)platformlar arası indirebilirsiniz.

> [!NOTE]
> PowerShell Core Ayrıca, veri bilimi ve iş analizi iş akışlarıyla birlikte çalışabilirliği göstermek için bazı örnekler için de kullanılır.

PowerShell Core yüklendikten sonra, geçerli oturumunuzda NWChem komutlarının kullanılabilir olması için `InvokeNWChem.psm1` içeri aktarın:

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

Bu, `Convert-NWChemToBroombridge` komutunu geçerli PowerShell oturumunda kullanılabilir hale getirir.
Docker 'daki gerekli görüntüleri indirmek ve bunları kullanarak NWChem giriş noktaları çalıştırıp, Kıosmbridge 'e çıktıyı yakalamak için aşağıdakileri çalıştırın:

```powershell
Convert-NWChemToBroombridge ./input.nw
```

Bu, `input.nw`NWChem ' i çalıştırarak bir Broombridge dosyası oluşturur.
Varsayılan olarak, Broombridge çıktısı giriş destesi ile aynı ada ve yola sahip olur ve `.nw` uzantısı `.yaml`ile değiştirilmiştir.
Bu, `Convert-NWChemToBroombridge`için `-DestinationPath` parametresi kullanılarak geçersiz kılınabilir.
Daha fazla bilgi, PowerShell 'in yerleşik yardım işlevleri kullanılarak elde edilebilir:

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```

