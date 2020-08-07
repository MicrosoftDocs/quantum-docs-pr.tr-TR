---
title: Örnek NWChem hisse programı
description: Bir NWChem giriş destesi kullanarak, hisse kualem simülasyonu için geçit sayısı alma örneği üzerinden ilerleyin.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
no-loc:
- Q#
- $$v
ms.openlocfilehash: 78d6488ed5e3972f85f1e6cf1ba2d197596c4cc3
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869316"
---
# <a name="end-to-end-with-nwchem"></a>NWChem ile uçtan uca #

Bu makalede, bir [Nwchem](http://www.nwchem-sw.org/index.php/Main_Page) giriş destesi 'nden başlayarak hisse Kualkem simülasyonu için geçit sayısı alma örneği hakkında yol göstereceğiz.
Bu örneğe devam etmeden önce, [yükleme ve doğrulama kılavuzunu](xref:microsoft.quantum.chemistry.concepts.installation)Izleyerek Docker 'ı yüklediğinizden emin olun.

Daha fazla bilgi için:
- [NWChem giriş noktaları yapısı](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [Hisse geliştirme seti ile kullanım için giriş destesi komutları](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [Kimya kitaplığı ve bağımlılıklarını yükleme](xref:microsoft.quantum.chemistry.concepts.installation)
- [Kaynak sayımı](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> Bu örnek için Windows PowerShell Core 'un çalıştırılması gerekir.
> Üzerinde Windows, macOS veya Linux için PowerShell Core 'u indirin https://github.com/PowerShell/PowerShell .

## <a name="importing-required-powershell-modules"></a>Gerekli PowerShell modülleri içeri aktarılıyor ##

Daha önce yapmadıysanız, hisse geliştirme seti ile çalışmaya yönelik örnekleri ve yardımcı programları içeren [Microsoft/hisse deposunu](https://github.com/Microsoft/Quantum)kopyalayın:

```powershell
git clone https://github.com/Microsoft/Quantum
```

Klonladıktan sonra `Microsoft/Quantum` `cd` `utilities/` klasöre uygulayın ve Docker ve nwchem Ile çalışmaya yönelik PowerShell modülünü içeri aktarın:

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> Varsayılan olarak, Windows tüm betiklerin veya modüllerin güvenlik ölçüsü olarak yürütülmesini önler.
> Windows 'da çalıştırmak gibi modüllere izin vermek için `Invoke-NWChem.psm1` , yürütme ilkesini değiştirmeniz gerekebilir.
> Bunu yapmak için şu komutu çalıştırın `Set-ExecutionPolicy` :
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> Daha sonra, PowerShell 'den çıktığınızda yürütme ilkesi geri döndürülür.
> Yürütme ilkesini kaydetmek isterseniz, şunun için farklı bir değer kullanın `-Scope` :
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

Artık komutun kullanılabilir olması gerekir `Convert-NWChemToBroombridge` :

```powershell
Get-Command -Module InvokeNWChem
```

Daha sonra, `Get-GateCount` **Getgatecount** örneği ile birlikte gelen komutunu içeri aktaracağız.
Tüm ayrıntılar için, [örnekle birlikte sunulan yönergelere](https://github.com/Microsoft/Quantum/tree/master/samples/chemistry/GetGateCount)bakın.
Ardından, `<runtime>` `win10-x64` `osx-x64` `linux-x64` işletim sisteminize bağlı olarak,, veya ile yerine şunu çalıştırın:

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

Artık komutun kullanılabilir olması gerekir `Get-GateCount` :

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a>Giriş noktaları ##

NWChem paketi bir _giriş destesi_ adlı bir metin dosyası alır ve bu, bellek ayırma ayarları gibi diğer parametrelerle birlikte, çözülmesi gereken bir hisse anı sorununu belirtir.
Bu örnekte, NWChem ile birlikte gelen önceden oluşturulmuş giriş desteklerden birini kullanacağız.
İlk olarak, [nwchemgit/nwchem deposunu](https://github.com/nwchemgit/nwchem)kopyalayın:

> [!NOTE]
> Bu çok büyük bir depo olduğundan, bağımsız değişkenini kullanarak bazı bant genişliğini ve disk alanını kaydetmek için basit bir kopya yapabiliriz `--depth 1` .
> Ancak bu isteğe bağlıdır.
> Kopyalama, olmadan sorunsuz çalışacaktır `--depth 1` .

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

`nwchemgit/nwchem`Depo, [ `QA/chem_library_tests` klasör](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests)altında listelenen hisse kullanımı için tasarlanan çeşitli giriş noktaları ile gelir.
Bu örnekte, `H4` giriş destesi kullanacağız:

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

Söz konusu olan moleule, bir açıda, `alpha` desteyi adında gösterildiği gibi belirli bir geometriye bağlı olan 4 Hydrogen ady sistemidir `h4_sto6g_alpha.nw` . H4, 1970s 'den beri hesaplama Kimya için bilinen bir [molesel kıyaslama](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) karşılaştırmasıdır. Bu parametre, deste 'ın, `sto6g` özellikle de 6 Gauss tabanlı işlevlere sahip bir [temel](https://en.wikipedia.org/wiki/STO-nG_basis_sets) değer olan bir gösterimle ilgili olarak bir gösterimi uyguladığı bir gösterimidir. Bu giriş destesi Ayrıca, nwchem Tenslı uygulama altyapısına (TCE), bu, hisse geliştirme seti ile birlikte çalışmak için gereken bilgileri oluşturmak üzere bir yol gösteren çeşitli yönergeler içerir:

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a>NWChem 'ten Brombridge çıkışı üretme ve kullanma ##

Artık, Brombridge belgelerini oluşturmak ve kullanmak için ihtiyacınız olan her şeye sahipsiniz.
NWChem çalıştırmak ve giriş destesi için bir Broombridge belgesi üretmek için `h4_sto6g_0.000.nw` şunu çalıştırın `Convert-NWChemToBroombridge` :

> [!NOTE]
> Bu komutu ilk kez çalıştırdığınızda Docker `nwchemorg/nwchem-qc` görüntüyü sizin için indirir.
> Bu işlem, bağlantı hızınıza bağlı olarak biraz zaman alabilir ve büyük olasılıkla kahve kupa alma fırsatı sağlar.

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

Bu, ile kullanabileceğiniz bir Broombridge belgesi üretir `h4_sto6g_0.000.yaml` `Get-GateCount` :

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
- Farklı ön tanımlı giriş noktaları deneyin, örneğin, içindeki parametresini değiştirerek `alpha` `h4_sto6g_alpha.nw` 
- NWChem Decks 'i doğrudan düzenleyerek, örneğin `STO-nG` farklı n, çeşitli seçenekler için modelleri inceleyerek 
- ' De bulunan diğer önceden tanımlı NWChem giriş çklarını deneyin `nwchem/qa/chem_library_tests`
- NWChem 'ten oluşturulan, önceden tanımlanmış bir Brombridge YAML değerlendirmeleri paketini deneyin ve [Microsoft/hisse deposu](https://github.com/Microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML)'nun bir parçası olarak kullanılabilir. Bu kıyaslamalar şunları içerir: 
    - molesel Hydrogen (H2), beryllium (be), Lityum hydride (LiH) gibi küçük molecules,
    - Ozone (O3), Beta-carotene, cytosinüs gibi daha büyük molecules ve çok daha fazlası. 
- Microsoft Quantum Development Kit bir arabirimi sunan grafiksel ön uç [Emsl oklarını](https://arrows.emsl.pnnl.gov/api/qsharp_chem) deneyin. 


## <a name="producing-broombridge-output-from-emsl-arrows"></a>EMSL oklarından Brombridge çıkışı üretme ##

Web tabanlı ön uç EMSL oklarını kullanmaya başlamak için [burada](https://arrows.emsl.pnnl.gov/api/qsharp_chem)bir tarayıcıda gezinin. 

> [!NOTE]
> Web tarayıcısında EMSL oklarını çalıştırmak, JavaScript 'In etkinleştirilmesini gerektirir. Tarayıcınızda JavaScript 'ı etkinleştirme hakkında daha fazla bilgi için lütfen bu [yönergelere](https://www.enable-javascript.com/) bakın. 

İlk olarak, sorgu kutusuna şöyle bir moleule girin``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.`` 

"1, 3, 7-Trimethylxanthine" yerine "Caffeine" gibi, kendi collokual adına göre birçok motacules girebilirsiniz. 

Sonra, görüntülenen düğmeye tıklayın ``theory{qsharp_chem}`` . Bu, sorgu kutusunu, çalışmayı, Kıosmbridge YAML biçimindeki çıktıyı dışa aktarmaya söyleyen bir yönergeyle birlikte doldurur. 

Şimdi, saat ``Run Arrows`` . Girişin boyutuna bağlı olarak bu işlem biraz zaman alabilir. Ya da, belirli bir modelin daha önce hesaplanmış olması durumunda, yalnızca bir veritabanındaki arama miktarına göre çok daha hızlı bir şekilde yapılabilir. Her iki durumda da, girinizin belirttiği deste karşı belirli bir NWChem çalıştırması hakkında bilgi içeren yeni bir sayfaya yönlendirilirsiniz. 

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

Yerel bir ``download`` kopyayı gibi benzersiz bir dosya adıyla kaydeden açık ' a tıklayın ``qsharp_chem48443.yaml`` (belirli bir ad her çalıştırma için farklı olacaktır). Daha sonra bu dosyayı yukarıdaki gibi daha fazla işleyebilirsiniz, örneğin, 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
kaynak sayısını almak için. 

EMSL okları başlangıç sayfasındaki sekmeden erişilebilen 3B moleule oluşturucusunun keyfini çıkarabilirsiniz ``Arrows Entry - 3D Builder`` . Gösterilen moleule 'in [Jsmol](http://wiki.jmol.org/index.php/JSmol) 3D resmine tıklanması, düzenleme yapmanıza izin verir. Au 'ler etrafında hareket ettirmek için, au 'ler arasındaki uzaklıklara göre değişiklik yapmak, au 'ler eklemek/kaldırmak gibi işlemler yapabilirsiniz. Bu seçimlerin her biri için, ``theory{qsharp_chem}`` sorgu kutusuna eklendikten sonra, Brombridge YAML şemasının bir örneğini oluşturabilir ve daha sonra hisse 
