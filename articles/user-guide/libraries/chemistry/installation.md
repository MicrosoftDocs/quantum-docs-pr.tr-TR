---
title: 'Microsoft Q # Chemistry kitaplığı yüklemesi'
description: Microsoft hisse Kimya kitaplığını yüklemeyi ve nwchem hesaplama Kimya platformuyla kullanmayı öğrenin.
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: 0e870bb3421dddb632375a2fc8633249954f8c8b
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871546"
---
# <a name="chemistry-library-installation"></a>Chemistry kitaplığı yüklemesi

[ **Molecularhydrogen** örneği](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) , el ile yapılandırılan molesel giriş verilerini kullanır.
Bu küçük örnekler için çok iyi olsa da, ölçekte ücretsiz olarak Hamiltonians milyon veya milyarlarca şart koşar.
Ölçeklenebilir hesaplama Kimya paketleri tarafından oluşturulan bu tür Hamiltonians, el ile içeri aktarmak için çok büyük.

Hisse geliştirme kiti için bulunan hisse dili Mistry kitaplığı, bilgi Kuzey Ulusal laboratuvarda çevre molesel bilimcları Laboratuvarı (emsl) tarafından geliştirilen, en özellikle [**nwchem**](http://www.nwchem-sw.org/) hesaplama Kimya platformunu hesaplama Kimya paketleri ile birlikte çalışacak şekilde tasarlanmıştır.
Özellikle, [ **Microsoft. hisse. kimya** paketi](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) , en son nwchem sürümleri tarafından dışarı aktarma için desteklenen [broombridge şeması](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)'nda temsil edilen hisse dili hatalı deneme simülasyonu sorunlarının örneklerini yüklemeye yönelik araçlar sağlar.

Hisse geliştirme seti Kimya kitaplığı, `qdk-chem` eski biçimler ve [broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)arasında dönüştürme için de bir komut satırı aracı sağlar.

Bu bölümde, Fchem ve Broombridge ya da eski biçimler ile hisse geliştirme setini kullanma hakkında ayrıntılı bilgi sağlanır `qdk-chem` .

## <a name="using-the-quantum-development-kit-with-nwchem"></a>NWChem ile hisse geliştirme setini kullanma

Bir ile NWChem kullanarak hızlı bir şekilde çalışmaya başlayın ve aşağıdaki yöntemlerden birini kullanın:

- [Integraldata/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML)konumundaki örneklerle birlikte sağlanan mevcut Broombridge dosyalarını kullanmaya başlayın.
- Yeni Brombridge sel giriş dosyaları oluşturmak için, NWChem için Web tabanlı bir ön uç olan [Microsoft Quantum Development Kit Için Emsl okları oluşturucusunu](https://arrows.emsl.pnnl.gov/api/qsharp_chem) kullanın.  
- NWChem çalıştırmak için PNNL tarafından sunulan [Docker görüntüsünü](https://hub.docker.com/r/nwchemorg/nwchem-qc/) kullanın veya
- Platformunuz için [NWChem derleme](http://www.nwchem-sw.org/index.php/Compiling_NWChem) .

Bilgi için bkz. nwchem [ile](xref:microsoft.quantum.chemistry.examples.endtoend) nasıl yapılır? ile nasıl yapılır? ile nasıl yapılır? ile nasıl yapılır?

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>Örneklerle sağlanan Broombridge dosyalarını kullanmaya başlama

Hisse geliştirme seti örnekleri deposundaki [Integraldata/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) klasörü, Brombridge, moleule veri dosyalarını içerir.  

Basit bir örnek olarak, Brombridge dosyalarından birinden Hamiltonian yüklemek için, [Getgatecount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) örneğini kullanın ve Fmıtonly algorigthms as kapılarının tahminlerini gerçekleştirin:

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
> [Windows Için Ubuntu 18,04 LTS](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)' yi yükledikten sonra, en `ubuntu18.04` sevdiğiniz terminalden çalıştırın ve kaynak kaynağı kaynağından nwchem 'yi yüklemek için yukarıdaki yönergeleri izleyin.

Kaynaktan NWChem derledikten sonra, nwchem `yaml_driver` giriş kımlarından hızla Broombridge örnekleri oluşturmak Için nwchem ile birlikte sunulan betiği çalıştırabilirsiniz:

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

Bu komut `input.yaml` , geçerli dizininizde Broombridge biçiminde yeni bir dosya oluşturur.

### <a name="using-nwchem-with-docker"></a>Docker ile NWChem kullanma

NWChem kullanımı için önceden oluşturulmuş görüntüler, [Docker Hub](https://hub.docker.com)aracılığıyla platformlar arası kullanılabilir.
Başlamak için platformunuzun Docker yükleme yönergelerini izleyin:

- [Ubuntu için Docker 'ı yükler](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [MacOS için Docker 'ı yükler](https://docs.docker.com/docker-for-mac/install/)
- [Docker for Windows 10 yüklemesi](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> Docker for Windows kullanıyorsanız, Docker daemon ile geçici dizininizi (genellikle bu sürücüdür) içeren sürücüyü paylaşmanız gerekir `C:\` . Daha fazla bilgi için bkz. [Docker belgeleri](https://docs.docker.com/docker-for-windows/#shared-drives) .

Docker yüklendikten sonra, görüntüyü çalıştırmak için hisse geliştirme seti örnekleri ile sağlanan PowerShell modülünü kullanabilir veya görüntüyü el ile çalıştırabilirsiniz.
PowerShell kullanarak burada ayrıntılandırıyoruz. Docker görüntüsünü el ile kullanmak isterseniz, lütfen [görüntüyle birlikte sunulan belgelere](https://hub.docker.com/r/nwchemorg/nwchem-qc/)bakın.

#### <a name="running-nwchem-through-powershell-core"></a>PowerShell Core ile NWChem çalıştırma

NWChem Docker görüntüsünü hisse geliştirme seti ile birlikte kullanmak için, dosyaları NWChem içinde ve dışında kullanarak, sizin için dosya taşımayı işleyen küçük bir PowerShell modülü sağlıyoruz.
PowerShell Core yüklü değilse, [GitHub 'Daki PowerShell deposundan](https://github.com/PowerShell/PowerShell#get-powershell)platformlar arası indirebilirsiniz.

> [!NOTE]
> PowerShell Core Ayrıca, veri bilimi ve iş analizi iş akışlarıyla birlikte çalışabilirliği göstermek için bazı örnekler için de kullanılır.

PowerShell Core yüklendikten sonra, `InvokeNWChem.psm1` geçerli oturumunuzda NWChem komutlarının kullanılabilmesini sağlamak için içeri aktarın:

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

Bu, `Convert-NWChemToBroombridge` komutu geçerli PowerShell oturumunda kullanılabilir hale getirir.
Docker 'daki gerekli görüntüleri indirmek ve bunları kullanarak NWChem giriş noktaları çalıştırıp, Kıosmbridge 'e çıktıyı yakalamak için aşağıdakileri çalıştırın:

```powershell
Convert-NWChemToBroombridge ./input.nw
```

Bu, NWChem on çalıştırarak bir Broombridge dosyası oluşturur `input.nw` .
Varsayılan olarak, Broombridge çıktısı, uzantısıyla değiştirildiği gibi, giriş destesi ile aynı ada ve yola sahip olacaktır `.nw` `.yaml` .
Bu, parametresi kullanılarak geçersiz kılınabilir `-DestinationPath` `Convert-NWChemToBroombridge` .
Daha fazla bilgi, PowerShell 'in yerleşik yardım işlevleri kullanılarak elde edilebilir:

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```

## <a name="using-the-quantum-development-kit-with-qdk-chem"></a>İle hisse geliştirme setini kullanma`qdk-chem`

Yüklemek için `qdk-chem` , komut satırında .NET Core SDK kullanabilirsiniz:

```dotnetcli
dotnet tool install --global Microsoft.Quantum.Chemistry.Tools
```

Yükledikten sonra `qdk-chem` , `--help` Aracı tarafından sunulan işlevsellik hakkında daha fazla ayrıntı almak için seçeneğini kullanabilirsiniz `qdk-chem` .

Broombridge 'e dönüştürmek için `qdk-chem convert` komutunu kullanabilirsiniz:

```
qdk-chem convert --from fcidump --to broombridge data.fcidump --out data.yml
```

`qdk-chem convert`Bu komut, verileri standart girişten de kabul edebilir ve standart çıktıya yazabilir; bu özellikle betikler içinde ve eski biçimlere dışa aktarma araçlarıyla tümleştirme için yararlıdır.
Örneğin, Bash içinde:

```bash
cat data.fcidump | qdk-convert --from fcidump --to broombridge - > data.yml
```
