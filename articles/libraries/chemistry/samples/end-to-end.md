---
title: Örnek NWChem hisse programı
description: Bir NWChem giriş destesi kullanarak, hisse kualem simülasyonu için geçit sayısı alma örneği üzerinden ilerleyin.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
ms.openlocfilehash: 545ade99859f2a9939477fb18604921f70a5d9aa
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906517"
---
# <a name="end-to-end-with-nwchem"></a>NWChem ile uçtan uca #

Bu sayfada, bir [Nwchem](http://www.nwchem-sw.org/index.php/Main_Page) giriş destesi 'nden başlayarak hisse Kualkem simülasyonu için geçit sayısı alma örneği hakkında yol göstereceğiz.
Bu örneğe devam etmeden önce, [yükleme ve doğrulama kılavuzunu](xref:microsoft.quantum.chemistry.concepts.installation)Izleyerek Docker 'ı yüklediğinizden emin olun.

Daha fazla bilgi için:
- [NWChem giriş noktaları yapısı](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [Hisse geliştirme seti ile kullanım için giriş destesi komutları](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [Kimya kitaplığı ve bağımlılıklarını yükleme](xref:microsoft.quantum.chemistry.concepts.installation)
- [Kaynak sayımı](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> Bu örnek için Windows PowerShell Core 'un çalıştırılması gerekir.
> https://github.com/PowerShell/PowerShelladresinden Windows, macOS veya Linux için PowerShell Core 'u indirin.

## <a name="importing-required-powershell-modules"></a>Gerekli PowerShell modülleri içeri aktarılıyor ##

Daha önce yapmadıysanız, hisse geliştirme seti ile çalışmaya yönelik örnekleri ve yardımcı programları içeren [Microsoft/hisse deposunu](https://github.com/Microsoft/Quantum)kopyalayın:

```powershell
git clone https://github.com/Microsoft/Quantum
```

`Microsoft/Quantum`kopyaladıktan sonra, `utilities/` klasöre `cd` gerçekleştirin ve Docker ve NWChem ile çalışmaya yönelik PowerShell modülünü içeri aktarın:

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> Varsayılan olarak, Windows tüm betiklerin veya modüllerin güvenlik ölçüsü olarak yürütülmesini önler.
> `Invoke-NWChem.psm1` gibi modüllerin Windows üzerinde çalışmasını sağlamak için yürütme ilkesini değiştirmeniz gerekebilir.
> Bunu yapmak için `Set-ExecutionPolicy` komutunu çalıştırın:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> Daha sonra, PowerShell 'den çıktığınızda yürütme ilkesi geri döndürülür.
> Yürütme ilkesini kaydetmek istiyorsanız `-Scope`için farklı bir değer kullanın:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

Artık `Convert-NWChemToBroombridge` komutu kullanılabilir olmalıdır:

```powershell
Get-Command -Module InvokeNWChem
```

Ardından, **Getgatecount** örneği ile birlikte sunulan `Get-GateCount` komutunu içeri aktaracağız.
Tüm ayrıntılar için, [örnekle birlikte sunulan yönergelere](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount)bakın.
Sonra, işletim sisteminize bağlı olarak, `<runtime>` `win10-x64`, `osx-x64`ya da `linux-x64`ile değiştirerek aşağıdakileri çalıştırın:

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

Artık `Get-GateCount` komutu kullanılabilir olmalıdır:

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a>Giriş noktaları ##

NWChem paketi bir _giriş destesi_ adlı bir metin dosyası alır ve bu, bellek ayırma ayarları gibi diğer parametrelerle birlikte, çözülmesi gereken bir hisse anı sorununu belirtir.
Bu örnekte, NWChem ile birlikte gelen önceden oluşturulmuş giriş desteklerden birini kullanacağız.
İlk olarak, [nwchemgit/nwchem deposunu](https://github.com/nwchemgit/nwchem)kopyalayın:

> [!NOTE]
> Bu çok büyük bir depo olduğundan, `--depth 1` bağımsız değişkenini kullanarak bazı bant genişliğini ve disk alanını kaydetmek için yüzeysel bir kopya yapabiliriz.
> Ancak bu isteğe bağlıdır.
> Kopyalama, `--depth 1`olmadan sorunsuz çalışacaktır.

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

`nwchemgit/nwchem` deposu, [`QA/chem_library_tests` klasörü](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests)altında listelenen hisse geliştirme seti ile kullanılmak üzere tasarlanan çeşitli giriş noktaları ile gelir.
Bu örnekte, `H4` giriş destesi kullanacağız:

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

Söz konusu moleule, belirli bir geometriye bağlı olan 4 Hydrogen alar sistemidir ve bu, `alpha`, destein ad `h4_sto6g_alpha.nw` gösterildiği gibi parametre. H4, 1970s 'den beri hesaplama Kimya için bilinen bir [molesel kıyaslama](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) karşılaştırmasıdır. `sto6g` parametresi, deste bir sdaha daha yüksek tür orbliğine göre bir temsili uyguladığından, özellikle de 6 Gauss tabanlı işlevlerle bir [Ung temelinde ayarlanmış](https://en.wikipedia.org/wiki/STO-nG_basis_sets) bir gösterimdir. Bu giriş destesi Ayrıca, nwchem Tenslı uygulama altyapısına (TCE), bu, hisse geliştirme seti ile birlikte çalışmak için gereken bilgileri oluşturmak üzere bir yol gösteren çeşitli yönergeler içerir:

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a>NWChem 'ten Brombridge çıkışı üretme ve kullanma ##

Artık, Brombridge belgelerini oluşturmak ve kullanmak için ihtiyacımız olan her şeyi sunuyoruz.
NWChem çalıştırmak ve `h4_sto6g_0.000.nw` giriş destesi için bir Broombridge belgesi oluşturmak için, `Convert-NWChemToBroombridge`çalıştırın:

> [!NOTE]
> Bu komutu ilk kez çalıştırdığınızda Docker `nwchemorg/nwchem-qc` görüntüsünü sizin için indirir.
> Bu işlem, bağlantı hızınıza bağlı olarak biraz zaman alabilir ve büyük olasılıkla kahve kupa alma fırsatı sağlar.

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

Bu, `Get-GateCount`ile kullanabilmemiz `h4_sto6g_0.000.yaml` adlı bir Broombridge belgesi üretir:

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

Artık, çeşitli hisse simülasyon yöntemleri için T-Count, döndürmeler sayısı, CNOT Count vb. gibi kaynak tahmini içeren konsol çıktısını görmeniz gerekir:

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

Buradan yapılacak çok sayıda şey vardır: 
- Farklı ön tanımlı giriş noktaları deneyin, örneğin, `h4_sto6g_alpha.nw``alpha` parametresi değiştirerek, 
- NWChem Decks 'i doğrudan düzenleyerek daha fazla n, örneğin çeşitli seçenekleri için `STO-nG` modellerini inceleyerek, bu noktaları değiştirmeyi deneyin. 
- `nwchem/qa/chem_library_tests`' de kullanılabilir olan diğer önceden tanımlı NWChem giriş çklarını deneyin,
- NWChem 'ten oluşturulan, önceden tanımlanmış bir Brombridge YAML değerlendirmeleri paketini deneyin ve [Microsoft/hisse deposu](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)'nun bir parçası olarak kullanılabilir. Bu kıyaslamalar şunları içerir: 
    - molesel Hydrogen (H2), beryllium (be), Lityum hydride (LiH) gibi küçük molecules,
    - Ozone (O3), Beta-carotene, cytosinüs gibi daha büyük molecules ve çok daha fazlası. 
- Microsoft Quantum Development Kit bir arabirimi sunan grafiksel ön uç [Emsl oklarını](https://arrows.emsl.pnnl.gov/api/qsharp_chem) deneyin. 


## <a name="producing-broombridge-output-from-emsl-arrows"></a>EMSL oklarından Brombridge çıkışı üretme ##

Web tabanlı ön uç EMSL oklarını kullanmaya başlamak için [burada](https://arrows.emsl.pnnl.gov/api/qsharp_chem)bir tarayıcıda gezinin. 

> [!NOTE]
> Web tarayıcısında EMSL oklarını çalıştırmak, JavaScript 'In etkinleştirilmesini gerektirir. Tarayıcınızda JavaScript 'ı etkinleştirme hakkında daha fazla bilgi için lütfen bu [yönergelere](https://www.enable-javascript.com/) bakın. 

İlk olarak, sorgu kutusuna şöyle bir moleule girin ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.`` 

"1, 3, 7-Trimethylxanthine" yerine "Caffeine" gibi, kendi collokual adına göre birçok motacules girebilirsiniz. 

Sonra, ``theory{qsharp_chem}``görüntülenen düğmeye tıklayın. Bu, sorgu kutusunu, çalışmayı, Kıosmbridge YAML biçimindeki çıktıyı dışa aktarmaya söyleyen bir yönergeyle birlikte doldurur. 

Şimdi, ``Run Arrows``saat. Girişin boyutuna bağlı olarak bu işlem biraz zaman alabilir. Ya da, belirli bir modelin daha önce hesaplanmış olması durumunda, yalnızca bir veritabanındaki arama miktarına göre çok daha hızlı bir şekilde yapılabilir. Her iki durumda da, girinizin belirttiği deste karşı belirli bir NWChem çalıştırması hakkında bilgi içeren yeni bir sayfaya yönlendirilirsiniz. 

Broombridge YAML dosyasını aşağıdaki üstbilgiyle başlayan bölümden indirip kaydedebilirsiniz: 
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

Yerel bir kopyayı ``qsharp_chem48443.yaml`` gibi benzersiz bir dosya adıyla kaydeden ``download``' a tıklayın (belirli ad her çalıştırma için farklı olur). Daha sonra bu dosyayı yukarıdaki gibi daha fazla işleyebilirsiniz, örneğin, 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
kaynak sayısını almak için. 

EMSL okları başlangıç sayfasındaki ``Arrows Entry - 3D Builder`` sekmesinden erişilebilen 3B moleule oluşturucusunun keyfini çıkarabilirsiniz. Gösterilen moleule 'in [Jsmol](http://wiki.jmol.org/index.php/JSmol) 3D resmine tıklanması, düzenleme yapmanıza izin verir. Au 'ler etrafında hareket ettirmek için, au 'ler arasındaki uzaklıklara göre değişiklik yapmak, au 'ler eklemek/kaldırmak gibi işlemler yapabilirsiniz. Bu seçeneklerin her biri için, sorgu kutusuna ``theory{qsharp_chem}`` eklendikten sonra Broombridge YAML şemasının bir örneğini oluşturabilir ve daha sonra hisse 
