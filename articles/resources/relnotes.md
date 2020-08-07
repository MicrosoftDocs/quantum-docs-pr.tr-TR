---
title: Microsoft Quantum Geliştirme Seti Sürüm Notları
description: Microsoft Quantum Geliştirme Seti önizlemesinde yapılan son güncelleştirmeler hakkında bilgi edinin.
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
uid: microsoft.quantum.relnotes
no-loc:
- Q#
- $$v
ms.openlocfilehash: 869d13acd5cb82fac73be514d6622a616ddceb54
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866681"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a>Microsoft Quantum Development Kit Sürüm Notları

Bu makale her Quantum Development Kit sürümüne ilişkin bilgileri içerir.

Yükleme yönergeleri için bu [yükleme kılavuzuna](xref:microsoft.quantum.install) başvurun.

Güncelleştirme yönergeleri için bu [güncelleştirme kılavuzuna](xref:microsoft.quantum.update) başvurun.


## <a name="version-01220072031"></a>Sürüm 0.12.20072031

*Yayın tarihi: 21 Temmuz 2020*

Bu sürüm aşağıdakileri içerir:

- Not defterlerinde açılan ad alanları Q# artık gelecekteki tüm hücre yürütmeleri için kullanılabilir. Bu, örneğin, ad alanlarının her kod hücresinde ilgili ad alanlarını açmak zorunda kalmadan, Not defterinin en üstündeki bir hücrede açılmasını sağlar. Yeni bir `%lsopen` Magic komutu, şu anda açık olan ad alanlarının listesini görüntüler.

[Kitaplıklar](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [derleyici](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [çalışma zamanı](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [örnekler](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [ı Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) ve [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)için kapalı PR 'ler tam listesine bakın.  

## <a name="version-01220070124"></a>Sürüm 0.12.20070124

*Yayın tarihi: 2 Temmuz 2020*

Bu sürüm aşağıdakileri içerir:

- `qdk-chem`Eski elektronik yapı sorun serileştirme biçimlerini (ör.: FCıDUMP) [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) 'e dönüştürmek için yeni araç
- Ad alanındaki yeni işlevler ve işlemler, [`Microsoft.Quantum.Synthesis`](xref:microsoft.quantum.synthesis) dönüştürme ve ayrıştırma tabanlı senklik algoritmaları kullanılarak klasik Oracles uygulanıyor.
- Q#Artık `%simulate` ,, `%estimate` ve diğer sihirli komutlara bağımsız değişkenlerin kullanılmasına izin veriyor. Daha fazla bilgi için bkz. [ `%simulate` sihirli komut başvurusu](xref:microsoft.quantum.iqsharp.magic-ref.simulate) .
- I 'de yeni aşama görüntüleme seçenekleri Q# . Daha fazla bilgi için bkz. [ `%config` sihirli komut başvurusu](xref:microsoft.quantum.iqsharp.magic-ref.config) .
- I Q# ve `qsharp` Python paketi artık Conda paketleri ([qsharp](https://anaconda.org/quantum-engineering/qsharp) ve [ıqsharp](https://anaconda.org/quantum-engineering/iqsharp)) aracılığıyla, Q# JUPITER ve Python işlevlerinin yerel yüklemesini bir Conda ortamına basitleştirmeye yardımcı olur. Daha fazla ayrıntı için bkz. [ Q# jupi Not defterleri](xref:microsoft.quantum.install.jupyter) ve [ Q# Python yükleme kılavuzlarıyla birlikte](xref:microsoft.quantum.install.python) .
- Simülatörü kullanırken, qubits 'in yayından sonra | 0 ⟩ durumunda olması gerekmez, ancak serbest bırakıldıktan hemen önce ölçüldüğünde otomatik olarak sıfırlanabilir.
- Q#Kullanıcıların, farklı QDK sürümleriyle kitaplık paketlerini kullanmasını kolaylaştıran, tam olarak aynı sürüm yerine yalnızca büyük & ikincil sürüm numaraları eşleşmesi gerektiren güncelleştirmeler
- Kullanım dışı bırakılan `Microsoft.Quantum.Primitive.*` ad alanı kaldırıldı
- Taşınan işlemler:
  - `Microsoft.Quantum.Intrinsic.Assert`Artık`Microsoft.Quantum.Diagnostics.AssertMeasurement`
  - `Microsoft.Quantum.Intrinsic.AssertProb`Artık`Microsoft.Quantum.Diagnostics.AssertMeasurementProbability`
- Hata düzeltmeleri 

[Kitaplıklar](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [derleyici](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [çalışma zamanı](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [örnekler](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [ı Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) ve [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)için kapalı PR 'ler tam listesine bakın.  

## <a name="version-0112006403"></a>Sürüm 0.11.2006.403

*Sürüm tarihi: 4 Haziran 2020*

Bu sürüm, projelerin derlemesini etkileyen bir hatayı düzeltir Q# .

## <a name="version-0112006207"></a>Sürüm 0.11.2006.207

*Sürüm tarihi: 3 Haziran 2020*

Bu sürüm aşağıdakileri içerir:

- Q#bir giriş noktası mevcut olduğunda not defterleri ve Python konak programları artık başarısız olmaz Q#
- Erişim değiştiricilerini kullanmaya yönelik [Standart kitaplık](xref:microsoft.quantum.libraries.standard.intro) güncelleştirmeleri
- Derleyici şimdi yerleşik yeniden yazma adımları arasında yeniden yazma adımlarının eklenmesine izin veriyor
- [API ilkelerimizde](xref:microsoft.quantum.contributing.api-design) açıklanan zamanlamaya uygun olarak, kullanım dışı bırakılan birkaç işlev ve işlem kaldırıldı. Q#sürüm 0.11.2004.2825 'de uyarı olmadan derleme yapan programlar ve kitaplıklar değiştirilmemiş olarak çalışmaya devam edecektir.

[Kitaplıklar](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [derleyici](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [çalışma zamanı](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [örnekler](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [ı Q# ](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) ve [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)için kapalı PR 'ler tam listesine bakın.  

> [!NOTE]
> Bu sürüm, projelerin derlemesini etkileyen bir hata içeriyor Q# . Daha yeni bir sürüme yükseltmenizi öneririz.

## <a name="version-01120042825"></a>Sürüm 0.11.2004.2825

*Sürüm tarihi: 30 Nisan 2020*

Bu sürüm aşağıdakileri içerir:

- Q#Artık C# veya Python ana bilgisayar dosyası gerektirmeyen komut satırı uygulamaları için yeni destek. Komut satırı uygulamalarıyla çalışmaya başlama hakkında daha fazla bilgi için Q# [buraya](xref:microsoft.quantum.install.standalone)bakın.
- Kuantum rastgele sayı oluşturucusu hızlı başlangıcı, artık C# veya Python konak dosyasına ihtiyaç duymayacak şekilde güncelleştirildi. Güncelleştirilmiş [Hızlı başlangıca](xref:microsoft.quantum.quickstarts.qrng) göz atın
- Q#Docker görüntülerinde performans iyileştirmeleri

> [!NOTE]
> Q#Yeni özniteliği kullanan komut satırı uygulamaları [`@EntryPoint()`](xref:microsoft.quantum.core.entrypoint) Python veya .net konak programlarından Şu anda çağrılamaz.
> Daha fazla bilgi için [Python](xref:microsoft.quantum.install.python) ve [.NET birlikte çalışabilirlik](xref:microsoft.quantum.install.cs) kılavuzlarına göz atın.

## <a name="version-01120033107"></a>Sürüm 0.11.2003.3107

*Sürüm tarihi: 31 Mart, 2020*

Bu sürüm, 0.11.2003.2506 sürümü için küçük hata düzeltmeleri içerir.

## <a name="version-01120032506"></a>Sürüm 0.11.2003.2506

*Sürüm tarihi: 26 Mart 2020*

Bu sürüm aşağıdakileri içerir:

- ' De erişim değiştiricileri için yeni destek Q# , daha fazla bilgi için bkz. [Dosya yapıları](xref:microsoft.quantum.guide.filestructure)
- .NET Core SDK 3.1’e güncelleştirildi

[Kitaplıklar](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [derleyici](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [çalışma zamanı](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [örnekler](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) ve [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)’lar için tam kapsamlı kapalı PR’ler listesine bakın.  

## <a name="version-01020022610"></a>Sürüm 0.10.2002.2610

*Sürüm tarihi: 27 Şubat 2020*

Bu sürüm aşağıdakileri içerir:

- Yeni Quantum Machine Learning kitaplığı, daha fazla bilgi için [QML belgeleri sayfamıza](https://docs.microsoft.com/quantum/libraries/machine-learning/?view=qsharp-preview) gidin
- Q#Hata düzeltmeleri, NuGet paketleri yüklenirken 10-20X performans artışına yol açar

[Kitaplıklar](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [derleyici](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [çalışma zamanı](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [örnekler](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) ve [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)’lar için tam kapsamlı kapalı PR’ler listesine bakın.  

## <a name="version-01020012831"></a>Sürüm 0.10.2001.2831

*Sürüm tarihi: 29 Ocak 2020*

Bu sürüm aşağıdakileri içerir:

- Yeni projeler oluştururken Microsoft.Quantum.Development.Kit NuGet paketinin yerini alacak yeni Microsoft.Quantum.SDK NuGet paketi. Microsoft.Quantum.Development.Kit NuGet paketi mevcut projeler için desteklenmeye devam edecek. 
- Q#Yeni Microsoft. hisse. SDK NuGet packge tarafından etkinleştirilen derleyici uzantıları için destek daha fazla bilgi Için [GitHub](https://github.com/microsoft/qsharp-compiler/tree/master/src/QuantumSdk#extending-the-q-compiler), [derleyici uzantıları örneği](https://github.com/microsoft/qsharp-compiler/tree/master/examples/CompilerExtensions) ve [ Q# dev bloguna](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/) bakın.
- .NET Core 3.1 desteği eklendi, daha eski .NET Core SDK sürümleriyle derleme işlemi sorunlara neden olabileceğinden 3.1.100 sürümünü yüklemeniz önemle önerilir
- Microsoft.Quantum.QsCompiler.Experimental altında yeni derleyici dönüşümleri kullanılabilir
- Çıkış durumu vektörlerinin I I 'de HTML olarak kullanıma sunulmasına yönelik yeni işlevsellikQ#
- Hadamard ve SWAP testleri için Microsoft.Quantum.Characterization’a EstimateFrequencyA desteği eklendi
- Yükseltilmiş Tudeamplifize ad alanı artık Q# Stil kılavuzunu kullanıyor

[Kitaplıklar](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [derleyici](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [çalışma zamanı](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [örnekler](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) ve [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)’lar için tam kapsamlı kapalı PR’ler listesine bakın.  

## <a name="version-01019120501"></a>Sürüm 0.10.1912.0501

*Sürüm tarihi: 5 Aralık 2019*

Bu sürüm aşağıdakileri içerir:

- Birim testi için yeni test özniteliği burada Q# GÜNCELLEŞTIRILMIŞ API belgelerine ve [here](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test) test & hata ayıklama kılavuzuna bakın [here](xref:microsoft.quantum.guide.testingdebugging)
- Program yürütme hatası durumunda yığın izlemesi eklendi Q#
- Visual Studio Code’da kesme noktaları desteğinin [OmniSharp C# Visual Studio Code uzantısında](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) güncelleştirilmesi gerekiyor

[Kitaplıklar](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [derleyici](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [çalışma zamanı](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [örnekler](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) ve [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)’lar için tam kapsamlı kapalı PR’ler listesine bakın.  

## <a name="version-01019111607"></a>Sürüm 0.10.1911.1607

*Sürüm tarihi: 17 Kasım 2019*

Bu sürüm aşağıdakileri içerir:

- [Quantum Katas](https://github.com/Microsoft/QuantumKatas) ve Jupyter Notebooks’a yönelik performans düzeltmeleri

[Kitaplıklar](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [derleyici](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [çalışma zamanı](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [örnekler](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) ve [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)’lar için tam kapsamlı kapalı PR’ler listesine bakın.  


## <a name="version-0101911307"></a>Sürüm 0.10.1911.307

*Sürüm tarihi: 1 Kasım 2019*

Bu sürüm aşağıdakileri içerir:

- Dil sunucusunu kendi içinde bir yürütülebilir dosya olarak dağıtmak ve .NET Core SDK sürüm bağımlılığını ortadan kaldırmak için Visual Studio Code ve Visual Studio uzantılarında yapılan güncelleştirmeler  
- .NET Core 3.0'a geçiş
- Yeni `Fail` yönteminin kullanıma sunulmasıyla Microsoft.Quantum.Simulation.Core.IOperationFactory'de hataya neden olan değişiklik. Yalnızca SimulatorBase'e kadar yayılmayan özel simülatörleri etkiler. Diğer ayrıntılar için [GitHub'da çekme isteğine bakın](https://github.com/microsoft/qsharp-runtime/pull/59).
- Kullanım dışı bırakılan öznitelikler için yeni destek

[Kitaplıklar](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [derleyici](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [çalışma zamanı](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [örnekler](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) ve [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)’lar için tam kapsamlı kapalı PR’ler listesine bakın.  

## <a name="version-0919093002"></a>Sürüm 0.9.1909.3002

*Sürüm tarihi: 30 Eylül 2019*

Bu sürüm aşağıdakileri içerir:

- Q#Visual Studio 2019 ' de kod tamamlamaya yönelik yeni destek (sürüm 16,3 & sonrası) & Visual Studio Code
- Kuantum ekleyicileri için yeni [Quantum Kata](https://github.com/Microsoft/QuantumKatas)

[Kitaplıklar](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [derleyici](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [çalışma zamanı](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [örnekler](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) ve [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)’lar için tam kapsamlı kapalı PR’ler listesine bakın.  

## <a name="version-09-packagereference-0919082902"></a>Sürüm 0.9 (*PackageReference 0.9.1908.2902*)

*Sürüm tarihi: 29 Ağustos 2019*

Bu sürüm aşağıdakileri içerir:

- İçindeki Birleşik bir [ifade](xref:microsoft.quantum.guide.operationsfunctions#conjugations) için yeni destekQ#
- Derleyiciye, “şununla değiştir”, “belge ekle”, ve tek dizili öğe güncelleştirmesi gibi yeni kod eylemleri eklendi
- Visual Studio Code uzantısına yükleme şablonu ve yeni proje komutları eklendi
- [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone) gibi yeni ApplyIf birleştiricisi çeşitleri eklendi
- Ek [Quantom Kata](https://github.com/Microsoft/QuantumKatas)’ları Jupyter Notebook’lara dönüştürüldü
- Visual Studio Uzantısı artık Visual Studio 2019’u gerektiriyor

[Kitaplıklar](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [derleyici](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [çalışma zamanı](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [örnekler](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) ve [Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)’lar için tam kapsamlı kapalı PR’ler listesine bakın.  

Mevcut programlarınızı yükseltmeye yönelik yönergelere ek olarak değişiklikler de burada özetlendi.  [ Q# Geliştirme bloguna](https://devblogs.microsoft.com/qsharp)bu değişiklikler hakkında daha fazla bilgi edinin.

## <a name="version-08-packagereference-0819071701"></a>Sürüm 0.8 (*PackageReference 0.8.1907.1701*)

*Sürüm tarihi: 12 Temmuz 2019*

Bu sürüm aşağıdakileri içerir:

- Dilimleme dizileri için yeni dizinleme konumları eklendi. Daha fazla bilgi için [dil başvurusuna bakın](xref:microsoft.quantum.guide.expressions#array-slices).
- [Microsoft Container Registry](https://github.com/microsoft/ContainerRegistry)barındırılan Dockerfile eklendi, [ Q# daha fazla bilgi için ı deposuna](https://github.com/microsoft/iqsharp/blob/master/README.md) bakın
- [İzleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) için hataya neden olan değişiklik, yapılandırma ayarları güncelleştirmesi, ad değişiklikleri. [Güncelleştirilmiş adlar için .NET API Tarayıcısına](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration) bakın.

[Kitaplıklar](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), ve [örnekler](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) için tam kapsamlı kapalı PR’ler listesine bakın.  

## <a name="version-07-packagereference-0719053109"></a>Sürüm 0.7 (*PackageReference 0.7.1905.3109*)

*Sürüm tarihi: 31 Mayıs 2019*

Bu sürüm aşağıdakileri içerir:
- Q#dile eklemeler, 
- kimya kitaplığı güncelleştirmeleri ve 
- yeni bir sayısal kitaplık.

[Kitaplıklar](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), ve [örnekler](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) için tam kapsamlı kapalı PR’ler listesine bakın.  

Mevcut programlarınızı yükseltmeye yönelik yönergelere ek olarak değişiklikler de burada özetlendi.  [ Q# Geliştirme bloguna](https://devblogs.microsoft.com/qsharp)bu değişiklikler hakkında daha fazla bilgi edinin.

### <a name="no-locq-language-syntax"></a>Q#Dil sözdizimi
Bu sürüm yeni Q# Dil sözdizimi ekler:
* [Kullanıcı tanımlı türler](xref:microsoft.quantum.guide.types#user-defined-types) için adlandırılmış öğeler eklendi.  
* Kullanıcı tanımlı tür oluşturucular artık işlev olarak kullanılabilir.
* Kullanıcı tanımlı türlerde [kopyala ve güncelleştir](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) ve [uygula ve yeniden ata](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) için destek eklendi.
* [Başarılı olana kadar yinele](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) döngülerine yönelik düzeltme bloğu artık isteğe bağlıdır.
* Artık işlevlerde while döngülerini destekliyoruz (işlemlerde desteklenmez).

### <a name="library"></a>Kitaplık 

Bu sürüm, sayısal bir kitaplık ekler: [Yeni sayısal kitaplığı kullanmayı](xref:microsoft.quantum.numerics.usage) öğrenin ve[yeni örnekleri](https://github.com/microsoft/quantum/tree/master/Numerics) deneyin.  [PR #102](https://github.com/Microsoft/QuantumLibraries/pull/102).  

Bu sürüm ile kimya kitaplığına yönelik genişletmeler ve güncelleştirmeler yeniden düzenlendi:
* Bileşenlerin modülerliği, genişletilebilirliği ve genel kod temizleme işlemi geliştirildi.  [PR #58](https://github.com/microsoft/QuantumLibraries/pull/58).
* Hem çok başvurulu dalga işlevleri hem de birleşik olarak bağlı kümeler olmak üzere [çok başvurulu dalga işlevlerine](xref:microsoft.quantum.chemistry.concepts.multireference) yönelik destek eklendi.  [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110).
* (Teşekkürler!) [1QBit](https://1qbit.com) için katkıda bulunan ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)): Ansatz kullanılarak gerçekleştirilen enerji değerlendirmesi. [PR #120](https://github.com/Microsoft/QuantumLibraries/pull/120).
* [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) şeması yeni [sürüm 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2)’ye yükseltildi ve birleşik ve bağlanmış küme belirtimi eklendi. [Sorun #65](https://github.com/microsoft/QuantumLibraries/issues/65).
* Kimya kitaplığı işlevlerine Python ile birlikte çalışma özelliği ekleme. Bu [örneği](https://github.com/microsoft/Quantum/tree/master/Chemistry/PythonIntegration)deneyin. [Sorun #53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110).

## <a name="version-061905"></a>Sürüm 0.6.1905

*Sürüm tarihi: 3 Mayıs 2019*

Bu sürüm aşağıdakileri içerir:
- dilde değişiklikler yapar Q# , 
- Quantum Development Kit kitaplıklarının yeniden yapılandırılması 
- eklenen yeni örnekler ve 
- düzeltilen hatalar.  [Kitaplıklar](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), ve [örnekler](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) için birkaç kapalı PR.  

Mevcut programlarınızı yükseltmeye yönelik yönergelere ek olarak değişiklikler de burada özetlendi.  Bu değişikler hakkında daha fazla bilgi edinmek için devblogs.microsoft.com/qsharp adresini ziyaret edin.

### <a name="no-locq-language-syntax"></a>Q#Dil sözdizimi
Bu sürüm yeni Q# Dil sözdizimi ekler:
* `+` işleçleriyle [kuantum işlemlerinin özelleştirmelerini ifade etmek için kısaltılmış bir yol](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations) (denetim ve eklenikler) eklendi.  Eski söz dizimi kullanımdan kaldırıldı.  Eski söz dizimini kullanan programlar (örneğin, `: adjoint`) çalışmaya devam eder ancak derleme zamanı uyarısı oluşturulur.  
* [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) için yeni bir işleç olan `w/` eklendi. Bu, dizi oluşturmayı mevcut bir dizinin değiştirilmesi olarak ifade etmek için kullanılabilir.
* Yaygın [uygula ve güncelleştir ifadesini](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols) (örneğin, `+=`, `w/=`) ekleyin.
* [Açık yönergelerdeki](xref:microsoft.quantum.guide.filestructure#open-directives) ad alanları için kısa ad belirtmeye yönelik yöntem eklendi.

Bu sürümle birlikte, bir dizi öğesinin ayarlanan deyimin sol tarafında belirtilmesine izin verilmeyecek.  Bunu, bu söz diziminin dizilerin değiştirilebilir olduğunu ima ettiği için gerçekleştirdik. Öyle ki, işlem her zaman yeni bir dizinin oluşturulmasıyla sonuçlandı.  Bunun yerine, aynı sonucu almak için yeni `w/` copy-and-update işlecinin kullanılmasını öneren bir derleyici hatası oluşturulacak.  

### <a name="library-restructuring"></a>Kitaplığı yeniden yapılandırma
Bu sürüm, tutarlı bir şekilde büyümelerine olanak tanımak için kitaplıkları yeniden yapılandırır:
* Microsoft.Quantum.Primitive ad alanını Microsoft.Quantum.Intrinsic olarak yeniden adlandırır.  Bu işlemler hedef makine tarafından uygulanır.  Microsoft.Quantum.Primitive ad alanı kullanım dışı bırakıldı.  Programlar işlemleri ve işlevleri kullanım dışı bırakılan adlar ile çağırdığında bir çalışma zamanı hatası öneride bulunur.

* Microsoft.Quantum.Canon paketini Microsoft.Quantum.Standard olarak yeniden adlandırır.  Bu paket çoğu program için ortak olan ad alanlarını içerir Q# .  Buna aşağıdakiler dahildir:  
    - Genel işlemler için Microsoft.Quantum.Canon
    - Genel amaçlı aritmetik işlemler için Microsoft.Quantum.Arithmetic
    - Qubit durumunu hazırlamak için kullanılan işlemler için Microsoft.Quantum.Preparation
    - Simülasyon işlevi için Microsoft.Quantum.Simulation

Bu değişiklik ile, program diğer yeni üç ad alanına taşınan işlemlere başvurursa Microsoft.Quatum.Canon ad alanına yönelik tek bir “aç” deyimi içeren programlarda derleme hatalarıyla karşılaşılabilir.  Üç yeni ad alanı için ek aç deyimleri eklenerek bu sorun kolayca çözülebilir.  

* İçerdiği işlemler diğer ad alanlarına taşındığı için bazı ad alanları kullanım dışı bırakıldı. Bu ad alanlarını kullanan programlar çalışmaya devam eder ve derleme zamanı uyarısı ad alanını işlemin tanımlandığı yerde gösterir.  

* Microsoft.Quantum.Arithmetic ad alanı, kullanıcı tanımlı <xref:microsoft.quantum.arithmetic.littleendian> türünü kullanması için normalleştirildi. Little endian’ın dönüştürülmesi gerektiğinde [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian) işlevini kullanın.  

* Çeşitli callables (işlevler ve işlemler) adları, [ Q# Stil kılavuzuna](xref:microsoft.quantum.contributing.style)uyacak şekilde değiştirilmiştir.  Eski çağrılabilir öğe adları kullanım dışı bırakıldı.  Eski çağrılabilir öğeleri kullanan programlar çalışmaya devam eder ancak bir derleme zamanı uyarısı oluşturulur. 

### <a name="new-samples"></a>New Örnekler

[ Q# F # sürücüsüyle kullanarak bir örnek](https://github.com/Microsoft/Quantum/pull/164)ekledik.  

**Teşekkürler!** http://github.com/Microsoft/Quantum konumunda yer alan açık kod tabanımıza katkıda bulunduğu için aşağıdaki katkıda bulunan kişiye teşekkürlerimiz sunarız. Bu katkılar, kodun zengin örneklerine önemli ölçüde sahiptir Q# :

* Mathias Soeken ([@msoeken](https://github.com/msoeken)): Oracle işlevi birleştirmesi. [PR #135](https://github.com/Microsoft/Quantum/pull/135).

### <a name="migrating-existing-projects-to-061905"></a>Mevcut projeleri 0.6.1905 sürümüne geçirme.

QDK’yı güncelleştirmek için [yükleme kılavuzuna](xref:microsoft.quantum.install) bakın.
  
Q#Hisse geliştirme setinin 0,5 sürümünden mevcut projeler varsa, bu projeleri en yeni sürüme geçirme adımları aşağıda verilmiştir.

    1. Projelerin sırayla yükseltilmesi gerekir.  Birden fazla proje içeren bir çözümünüz varsa, her projeyi başvurulma sırasına göre güncelleştirin.
    2. Mevcut tüm ikilileri ve ara dosyaları kaldırmak için komut satırında `dotnet clean` komutunu çalıştırın.
    3. Tüm “Microsoft.Quantum” `PackageReference` sürümlerini 0.6.1904 olarak değiştirmek için bir metin düzenleyicide .csproj dosyasını düzenleyin ve “Microsoft.Quantum.Canon” paketinin adını “Microsoft.Quantum.Standard” olarak değiştirin. Örneğin:

         ```xml
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
        ```
    4. Komut satırında bu komutu çalıştırın: `dotnet msbuild`  
    5. Bunu çalıştırdıktan sonra, yukarıda listelenen değişikliklerden ötürü hataları el ile düzeltmeniz gerekebilir.  Çoğu durumda, bu hatalar Visual Studio veya Visual Studio Code’daki IntelliSense tarafından da raporlanır.
        - Projenin kök klasörünü veya içerilen çözümü Visual Studio 2019 veya Visual Studio Code’da açın.
        - Düzenleyicide bir. QS dosyası açtıktan sonra, Q# Çıkış penceresinde dil uzantısının çıkışını görmeniz gerekir.
        - Proje başarıyla yüklendikten sonra (çıkış penceresinde gösterilir), her dosyayı açıp kalan tüm sorunları el ile düzeltin.

> [!NOTE]
> * 0\.6 sürümü için, Quantum Development Kit ile sunulan dil sunucusu birden fazla çalışma alanını desteklemez.
> * Visual Studio Code’da bir proje üzerinde çalışmak için projeyi içeren kök klasörü ve başvurulan tüm projeleri açın.   
> * Visual Studio Code’da bir çözüm üzerinde çalışmak için çözümde yer alan tüm projelerin çözüm ile aynı klasörde veya bunun bir alt klasöründe olması gerekir.  
> * 0\.6 veya daha yeni bir sürüme geçirilen projeler ve eski paket sürümlerini kullanan projelerin arasındaki başvurular **desteklenmez**.

## <a name="version-051904"></a>Sürüm 0.5.1904

*Sürüm tarihi: 15 Nisan 2019*

Bu sürüm hata düzeltmelerini içerir.


## <a name="version-051903"></a>Sürüm 0.5.1903

*Sürüm tarihi: 27 Mart 2019*

Bu sürüm aşağıdakileri içerir:

- Hakkında bilgi edinmek için harika bir yol sunan Jupyter Notebook için destek ekler Q# .  [Yeni Jupyter Notebook örneklerine göz atın ve kendi Notebook’larınızı yazmayı öğrenin](xref:microsoft.quantum.install). 

- Quantum Canon kitaplığına tamsayı ekleyici aritmetiğini ekler.  [Yeni tamsayı ekleyicilerini kullanmayı açıklayan](https://github.com/microsoft/Quantum/blob/master/samples/arithmetic/AdderExample.ipynb) Jupyter Notebook’una da bakın.

- Topluluk tarafından bildirilen DumpRegister sorununa yönelik hata düzeltmesi ([#148](https://github.com/Microsoft/Quantum/issues/148)).

- [Using deyiminden](xref:microsoft.quantum.guide.qubits#allocating-qubits) dönme özelliği eklendi.

- [Başlangıç kılavuzu](xref:microsoft.quantum.install) yenilendi.


## <a name="version-051902"></a>Sürüm 0.5.1902

*Sürüm tarihi: 27 Şubat 2019*

Bu sürüm aşağıdakileri içerir:

- Platformlar arası Python konağına yönelik destek eklendi.  `qsharp`Python paketi, Q# Python içinden işlem ve işlevlerin benzetimini yapmayı kolaylaştırır. [Python ile birlikte çalışabilirlik](xref:microsoft.quantum.install) hakkında daha fazla bilgi edinin. 

- Visual Studio ve Visual Studio Code uzantıları artık sembollerin yeniden adlandırılmasını (örn. işlevler ve işlemler) destekler.

- Visual Studio uzantısı artık Visual Studio 2019’a yüklenebilir.

## <a name="version-041901"></a>Sürüm 0.4.1901

*Sürüm tarihi: 30 Ocak 2019*

Bu sürüm aşağıdakileri içerir:

- Boyutu isteğe bağlı olarak değiştirilebilen bir işaretli tamsayıyı gösteren yeni temel öğe BigInt için destek eklendi.  [BigInt türü](xref:microsoft.quantum.guide.types) hakkında daha fazla bilgi edinin.
- Çok fazla sayıda qubit ile X, CNOT ve birden fazla öğe tarafından denetlenen X kuantum işleminin simülasyonunu yapabilen özel amaçlı hızlı bir simülatör olan Toffoli simülatörü eklendi.  [Toffoli simülatörü hakkında](xref:microsoft.quantum.machines.toffoli-simulator) daha fazla bilgi edinin.
- bir hisse bilgisayar üzerinde bir işlemin belirli bir ınstancee 'sini çalıştırmak için gereken kaynakları tahmin eden basit bir kaynak tahminleyicisi ekler Q# .  [Kaynak tahmin aracı](xref:microsoft.quantum.machines.resources-estimator) hakkında daha fazla bilgi edinin.


## <a name="version-0318112802"></a>Sürüm 0.3.1811.2802

*Sürüm tarihi: 28 Kasım 2018*

VS Code uzantımızın bunu kullanmıyor olmasına rağmen bu öğeye bayrak eklendi ve `event-stream` NPM paketine ilişkin [uzantı temizliği](https://code.visualstudio.com/blogs/2018/11/26/event-stream) esnasında bu öğe marketten kaldırıldı. Bu sürüm, uzantının kırmızı bayrak tetiklemesine sebep olabilecek tüm çalışma zamanı bağımlılıklarını kaldırır.

Uzantıyı daha önceden yüklediyseniz, Visual Studio Market’te [Visual Studio Code için Microsoft Quantum Development Kit](vscode:extension/quantum.quantum-devkit-vscode)’i ziyaret edip Yükle’ye basarak bunu yeniden yüklemeniz gerekir. Bu sorundan dolayı özür dileriz.


## <a name="version-0318111511"></a>Sürüm 0.3.1811.1511

*Sürüm tarihi: 20 Kasım 2018*

Bu sürüm, bazı kullanıcıların Visual Studio uzantısını başarıyla yüklemesine engel olan bir hatayı düzeltir.

## <a name="version-031811203"></a>Sürüm 0.3.1811.203

*Sürüm tarihi: 2 Kasım 2018*

Bu sürüm, aşağıdakiler de dahil olmak üzere birkaç hata düzeltmesini içerir:

* `DumpMachine` çağrıldığında, bazı belirli durumlarda simülatörün durumunun değişmesi.
* .NET Core’un 2.1.403’ten önceki sürümleri kullanıldığında proje oluşturulurken karşılaşılan derleme uyarıları kaldırıldı.
* Belgeler, özellikle de VS Code veya Visual Studio’da imleç öğenin üzerine getirildiğinde gösterilen araç ipuçları temizlendi.

## <a name="version-0318102508"></a>Sürüm 0.3.1810.2508

*Sürüm tarihi: 29 Ekim 2018*

Bu sürüm, yeni dil özellikleri içerir ve geliştirici deneyimini iyileştirir:

* Bu sürümde, için bir dil sunucusu Q# , Ayrıca Visual Studio için istemci tümleştirmeleri ve Visual Studio Code dahildir. Bu, hata ve uyarıların dalgalı alt çizgileri biçiminde yazmaya yönelik canlı geri bildirimin yanı sıra yeni IntelliSense özellikleriyle yazma olanağı tanır. 
* Bu güncelleştirme, tanılama için kolay gezinti ve hassas aralıklar ve öğenin üzerine gelindiğinde gösterilen ek ayrıntılar ile tanılama iletilerini büyük ölçüde geliştirir.
* Q#Bu dil, geliştiricilerin genel işlemleri yapabildiği ve powertam Express hisse hesaplamalarına yönelik dil özelliklerine yönelik yeni geliştirmelerin yollarını birleştiren yollarla genişletilmiştir.  Bu sürümle birlikte dilde bir çok büyük değişiklikler var Q# .   

Bu sürüm yeni bir kuantum kimyası kitaplığını da içerir:

* Kimya kitaplığı, aşağıdakilerin de dahil olduğu yeni bir Hamiltonian simülasyonu özelliklerini içerir:
    - Gelişmiş simülasyon doğruluğu için isteğe bağlı çift sıralı Trotter–Suzuki tümleştiricileri.
    - $T$-gate karmaşıklığını azaltmaya yönelik kimyaya özel iyileştirmeler ile Qubitization simülasyonu tekniği.
* Moleküllerin gösterimini içeri aktarmak ve bunların simülasyonunu yapmak için Broombridge Şeması (Hamiltonian’ların doğum yeri olarak kabul edilen bir [yer işaretini](https://en.wikipedia.org/wiki/Broom_Bridge) belirtir) adlı yeni bir açık kaynak şema sunuldu.
* Broombridge Şeması kullanılarak tanımlanan birden fazla kimyasal gösterim sunulur.  Bu modeller, açık kaynaklı ve yüksek performanslı bir hesaplamalı kimya aracı olan [NWChem](http://www.nwchem-sw.org/) kullanılarak oluşturuldu.
* Öğreticiler ve Örnekler, aşağıdakileri gerçekleştirmek için kimya kitaplıklarını ve Broombridge veri modelleri kullanmayı açıklar:
    - Kimya kitaplığını kullanarak basit Hamiltonian’lar oluşturma
    - Faz tahmini kullanarak topraklanmış ve uyarılmış lityum hidrit enerjilerini görselleştirme.
    - Kuantum kimyası simülasyonuna yönelik kaynak tahminleri gerçekleştirme.
    - Broombridge şeması tarafından gösterilen moleküllerin enerji düzeyini tahmin etme.
* Belgeler, ile hisse benzetiminin ek kimyasal modellerini oluşturmak için NWChem 'in nasıl kullanılacağını açıklar Q# .

[Quantum Development Kit kimya kitaplığı](xref:microsoft.quantum.chemistry.concepts.intro) hakkında daha fazla bilgi edinin.

Yeni kimya kitaplığı ile kitaplıkları yeni bir GitHub deposuna [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries) ayırıyoruz.  Örnekler [Microsoft/Quantum](https://github.com/Microsoft/Quantum) deposunda kalır.  Her ikisine yönelik katkılarınızı bekliyoruz!

Bu sürüm, topluluk tarafından bildirilen sorunlara yönelik hata düzeltmelerini ve özellikleri içerir:

* IntelliSense için Q# ? ([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918)).
* .qs dosyaları ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049)).
* İf deyiminde küme ayraçları kısaltıldığında oluşan hata iletisi geliştirildi ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518)).
* Değiştirilebilir (yeniden) bağlama işleminde tanımlama grubu ayrıştırma desteği ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444)).
* Sağlanan BitFlipCode Çalıştırılırken Oluşan Hata ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).
* H2SimulationGUI’nin bazen çok yüksek tepe değerleri göstermesi ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370)).

### <a name="community-contributions"></a>Topluluk Katkıları

**Teşekkürler!** http://github.com/Microsoft/Quantum konumunda yer alan açık kod tabanımıza yönelik katkıları için aşağıdaki katkıda bulunanlara teşekkür ederiz. Bu katkılar, kodun zengin örneklerine önemli ölçüde sahiptir Q# :

* Rolf Kuisman ( [@RolfHuisman](https://github.com/RolfHuisman) ): qasm/ Q# geliştiriciler IÇIN BIR qasm ile Translator oluşturma deneyimi geliştirilmiştir Q# . [PR #58](https://github.com/Microsoft/Quantum/pull/58).

* Andrew Helwer ([@ahelwer](https://github.com/ahelwer)):  ilişkin bir kuantum oyunu olan CHSH Game’i uygulayan bir örnek ile katkıda bulundu.  [PR #84](https://github.com/Microsoft/Quantum/pull/84).

Belgeler, yazım ve imla düzeltmeleri ile içeriğin düzeltilmesine yönelik çalışmalarından ötürü Rohit Gupta ([@guptarohit](https://github.com/guptarohit),[PR #90](https://github.com/Microsoft/quantum/pull/90)), Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi),[PR #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)), ve Lee James O’Riordan’a ([@mlxd](https://github.com/mlxd),[PR #96](https://github.com/Microsoft/Quantum/pull/96)) da teşekürlerimizi sunarız! 

## <a name="version-021809701"></a>Sürüm 0.2.1809.701

*Sürüm tarihi: 10 Eylül 2018*

Bu sürüm, topluluk tarafından bildirilen sorunlara yönelik hata düzeltmelerini içerir. Şunları içerir:

* Shift işlecinin kullanılamaması ([GitHub](https://github.com/Microsoft/Quantum/issues/75)).
* `DumpMachine` / `DumpRegister` öğesinin konsola yazdırılırken `QCTraceSimulator` aşamasında başarısız olması ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680)).
* 0 qubitin ayrılmasına izin verme ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits)).
* `AssertQubitState` öğesinin açık Complex() çağrısı gerektirmesi ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call)).
* `Measure` işleminin macOS’de her zaman `One` döndürmesi ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).

Teşekkür ederiz! 

## <a name="version-0218063001"></a>Sürüm 0.2.1806.3001

*Sürüm tarihi: 30 Haziran 2018*

Bu sürümler, [GitHub 'da bildirilen #48 soruna](https://github.com/Microsoft/Quantum/issues/48) yönelik hızlı bir düzeldir ( Q# Kullanıcı adı boş bir boşluk içeriyorsa derleme başarısız olur). İlgili yeni sürümde de (`0.2.1806.3001-preview`) `0.2.1806.1503` öğesindeki güncelleştirme yönergelerini izleyin.

## <a name="version-0218061503"></a>Sürüm 0.2.1806.1503

*Sürüm tarihi: 22 Haziran 2018*

Bu sürüm, topluluk için yapılan birkaç katkıyı, geliştirilmiş hata ayıklama deneyimini ve iyileştirilmiş performansı içerir.  Daha ayrıntılı şekilde belirtmek gerekirse:

* QuantumSimulator hedef makinesine yönelik küçük ve büyük simülasyonlarda performans iyileştirmeleri.
* Hata ayıklama işlevi geliştirildi.
* Hata düzeltmelerinde, yeni yardımcı işlevlerinde, işlemlerde ve yeni örneklerde topluluk katkıları.

### <a name="performance-improvements"></a>Performans iyileştirmeleri

Bu güncelleştirme, hedeflenen tüm makinelerdeki çok ve az sayıdaki qubitlere yönelik önemli performans iyileştirmelerini içerir.  Bu geliştirme, Quantum Development Kit’te standart bir örnek olan H<sub>2</sub> simülasyonu ile kolayca görülebilir.

### <a name="improved-debugging-functionality"></a>Hata ayıklama işlevi geliştirildi

Bu güncelleştirme ile yeni hata ayıklama işlevi eklendi:
* Zaman içinde hedef kuantum makinesi hakkında işlev bilgileri çıkışı veren iki yeni işlem (@"microsoft.quantum.extensions.diagnostics.dumpmachine" ve @"microsoft.quantum.extensions.diagnostics.dumpregister") eklendi.  
* Visual Studio’da, tek bir qubitte $\ket{1}$ öğesinin ölçüm olasılığı artık hedef makineye yönelik QuantumSimulator’ın hata ayıklama penceresinde otomatik olarak gösterilir.
* Visual Studio’da **İfade ve Değişkenler** ve **Yerel Öğeler** hata ayıklama pencerelerindeki çeşitli özelliklerin görünümü geliştirildi. 

[Test etme ve Hata ayıklama](xref:microsoft.quantum.guide.testingdebugging) hakkında daha fazla bilgi edinin.

### <a name="community-contributions"></a>Topluluk Katkıları

Q#Kodlayıcı topluluğu büyümekte ve üzerinde açık kod temelimize gönderilen ilk Kullanıcı kitaplıklarını ve örnekleri görmek için çok http://github.com/Microsoft/quantum .  **Çok teşekkürler!** Aşağıdaki katkıda bulunanlara teşekkürlerimizi sunarız:
* Mathias Soeken ([@msoeken](https://github.com/msoeken)):  belirli bir permütasyonu uygulamaya yönelik Toffoli ağlarını oluşturan dönüşüm temelli mantık birleştirme yöntemini tanımlayan bir örnek ile katkıda bulundu. Kod tamamen Q# işlevlerde ve işlemlerde yazılır.  [PR #41](https://github.com/Microsoft/Quantum/pull/41).
* RolfHuisman ( [@RolfHuisman](https://github.com/RolfHuisman) ): MICROSOFT MVP Rolf Kuisman, Q# Klasik denetim akışı ve kısıtlı hisse işlemleri olmayan kısıtlanmış bir program sınıfı için koddan düz qasm kodu üreten bir örneğe katkıda bulunur. [PR #59](https://github.com/Microsoft/Quantum/pull/59)
* Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314)): denetimli işlemler için kitaplık işlevi göndererek kod temelimizin geliştirilmesine yardımcı oldu. [PR #53](https://github.com/Microsoft/Quantum/pull/53)
* Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111)): @"microsoft.quantum.canon.quantumphaseestimation" öğesini düzeltti ve yeni birim testleri oluşturdu.  [PR #54](https://github.com/Microsoft/Quantum/pull/54)
* Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit)): QuantumSimulator örneğinin atılmasını sağlayarak Teleportation örneğini temizledi. [PR #20](https://github.com/Microsoft/Quantum/pull/20)

Sizlere de **Teşekkürler!** Hackathon esnasında belgelerimizde değerli değişiklikler yapan Ticari Mühendislik Hizmetleri ekibinin katkıda bulunanlarında yer alan bu Microsoft Yazılım Mühendislerine de teşekkürlerimizi sunarız.  Yaptıkları değişiklikler hepimiz için açıklığı ve ekleme deneyimini geliştirdi:
* Sascha Corti
* Mihaela Curmei
* John Donnelly
* Kirill Logachev
* Jan Pospisil
* Anita Ramanan
* Frances Tibble
* Alessandro Vozza

### <a name="update-existing-projects"></a>Mevcut projeleri güncelleştirme

Bu sürüm tamamen geriye dönük olarak uyumludur. Projelerinizdeki NuGet paketlerini sürüm `0.2.1806.1503-preview` olacak şekilde yükseltip tüm ara dosyaların yeniden üretildiğinden emin olmak için **tam kapsamlı bir yeniden derleme** yapın.

Visual Studio’da [paketi güncelleştirmeye yönelik](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package) normal yönergeleri izleyin.

Komut satırına yönelik proje şablonlarını güncelleştirmek için aşağıdaki komutu çalıştırın:
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

Bu komut çalıştırıldıktan sonra, `dotnet new <project-type> -lang Q#` kullanılarak oluşturulan tüm yeni projeler otomatik olarak Quantum Development Kit’in bu sürümünü kullanır.

Mevcut bir projeyi yeni sürümü kullanacak şekilde güncelleştirmek için her projenin dizininde aşağıdaki komutu çalıştırın:

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

Mevcut bir proje, birim testi için XUnit tümleştirmesini de kullanıyorsa, bu paketi de güncelleştirmek için benzer bir komut kullanılabilir:
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

Test projenizin kullandığı XUnit sürümüne bağlı olarak XUnit’i 2.3.1 sürümüne güncelleştirmeniz de gerekebilir.
```
dotnet add package xunit -v "2.3.1" 
```

Güncelleştirmeden sonra, şunu yaparak önceki sürüm tarafından oluşturulan tüm geçici dosyaları kaldırdığınızdan emin olun:
```
dotnet clean 
```

### <a name="known-issues"></a>Bilinen Sorunlar

Raporlanacak bilinen ek sorun yok.


## <a name="version-0218022202"></a>Sürüm 0.2.1802.2202

*Sürüm tarihi: 26 Şubat 2018*

Bu sürüm, daha fazla platformda geliştirmeye, dillerin birlikte çalışabilirliğine ve performans geliştirmelerine yönelik destek sunar. Daha ayrıntılı şekilde belirtmek gerekirse:

- macOS ve Linux tabanlı geliştirmeye yönelik destek. 
- Platformlar arası Visual Studio Code desteğini de içeren .NET Core uyumluluğu.
- Quantum Development Kit Kitaplıkları için tam kapsamlı bir Açık Kaynak lisansı.
- 20 veya daha fazla qubit gerektiren projelerde simülatör performansı geliştirildi.
- Python diliyle birlikte çalışabilme özelliği (önizleme sürümü Windows’ta sunulur).

### <a name="net-editions"></a>.NET Sürümleri

.NET platformu, Windows ile sunulan .NET Çerçevesi ve Windows, macOS ve Linux ile sunulan açık kaynak .NET Core olmak üzere iki farklı sürüm olarak sunulur.
Bu sürüm ile, Quantum Development Kit’in çoğu parçası hem Framework hem de Core’da ortak sınıf kümeleri olan .NET Standard’a yönelik kitaplıklar olarak sunulur.
Bu nedenle, bu kitaplıklar .NET Framework veya .NET Core’un son zamanlarda sunulan sürümleriyle uyumludur.

Bu nedenle, Quantum Development Kit kullanılarak yazılan projelerin mümkün olduğunca taşınabilir olmasını sağlamak için Quantum Development Kit kullanılarak yazılan kitaplık projelerinin .NET Standard’ı konsol uygulamalarının da .NET Core’u hedeflemesini öneririz.
Quantum Development Kit’in önceki sürümleri yalnızca .NET Framework’ü desteklediği için mevcut projelerinizi geçirmeniz gerekebilir. Bunu yapmaya yönelik ayrıntılar için aşağıya bakın.

### <a name="project-migration"></a>Proje Geçişi

Bunlarda kullanılan NuGet paketlerini güncelleştirmediğiniz sürece Quantum Development Kit’in önceki sürümleri kullanılarak oluşturulan projeler çalışmaya devam eder. Mevcut kodu yeni sürüme geçirmek için aşağıdaki adımları gerçekleştirin:
1. Doğru Q# proje şablonu türünü (uygulama, kitaplık veya test projesi) kullanarak yeni bir .NET Core projesi oluşturun.
2. (Ekle > Mevcut Öğe’yi kullanarak) mevcut .qs ve .cs/.fs dosyalarını eski projeden yeni projeye kopyalayın. AssemblyInfo.cs dosyasını kopyalamayın.
3. Yeni projeyi oluşturup çalıştırın.

Microsoft.Quantum.Canon ad alanındaki RandomWalkPhaseEstimation işleminin [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc) deposundaki Microsoft.Research.Quantum.RandomWalkPhaseEstimation ad alanına taşındığını unutmayın.

### <a name="known-issues"></a>Bilinen Sorunlar

- `--filter`Seçeneği `dotnet test` ' de yazılan testler için doğru çalışmıyor Q# .
  Bunun sonucu olarak, bireysel birim testleri Visual Studio Code’da çalıştırılamaz. Tüm testleri çalıştırmak için komut satırında `dotnet test` öğesini kullanmanızı öneririz.

## <a name="version-0118011707"></a>Sürüm 0.1.1801.1707

*Sürüm tarihi: 18 Ocak 2018*

Bu sürüm ile topluluk tarafından bildirilen bazı sorunları düzeltildi. Bu sorunlar şunlardır:

- Simülatör artık AVX’in etkinleştirildiği eski CPU’larda çalışır.
- Bölgesel ondalık ayarları, Q# ayrıştırıcısının başarısız olmasına neden olmaz.
- `SignD` temel işlemi artık `Double` değerinden ziyade `Int` döndürür.


## <a name="version-011712901"></a>Sürüm 0.1.1712.901

*Sürüm tarihi: 11 Aralık 2017*

### <a name="known-issues"></a>Bilinen Sorunlar

#### <a name="hardware-and-software-requirements"></a>Donanım ve Yazılım Gereksinimleri

- Quantum Development Kit ile sunulan simülatörü çalıştırmak için Microsoft Windows’un 64 bit kurulumu gerekir.
- Quantum Development Kit ile yüklenen Microsoft’un kuantum simülatörü Gelişmiş Vektör Uzantıları (AVX) kullanır ve AVX’in etkinleştirildiği bir CPU’yu gerektirir. Q1 2011 (Sandy Bridge) veya daha sonra çıkan Intel işlemciler AVX’i destekler. Daha önce çıkan CPU’lara yönelik desteği değerlendiriyoruz ve ayrıntıları daha sonra açıklayabiliriz.

#### <a name="project-creation"></a>Proje Oluşturma

- Tarafından kullanılacak bir çözüm (. sln) oluştururken çözüm, Q# çözümdeki her projeden (. csproj) daha yüksek bir dizin olmalıdır. Bu, yeni bir çözüm oluştururken “Yeni Proje” iletişim kutusundaki “Çözüme yönelik dizin oluştur” onay kutusu işaretlenerek gerçekleştirilebilir. Bu yapılmazsa, Quantum Development Kit NuGet paketlerinin el ile yüklenmesi gerekir.

#### Q#

- IntelliSense, kod için doğru hataları görüntülemez Q# . Doğru hataları görmek için Visual Studio Hata Listesi derleme hatalarını görüntülediğinizden emin olun Q# . Ayrıca, Q# bir derlemeyi tamamladıktan sonra hataların gösterilmediğini unutmayın.
- Kısmi bir uygulamada değiştirilebilir bir dizi kullanılması beklenmeyen davranışlara neden olabilir.
- Sabit bir dizinin değiştirilebilir bir diziye (b’nin değiştirilebilir bir dizi olduğu yerde a = b’ye izin verin) bağlanması beklenmeyen davranışlar neden olabilir.
- Profil oluşturma, kod kapsamı ve diğer VS eklentileri her zaman Q# satırları ve blokları doğru bir şekilde saymayabilir.
- Q#Derleyici, enterpolasyonlu dizeleri doğrulamaz. Değişken adlarını yanlış yazarak veya enterpolasyonlu dizelerde ifadeleri kullanarak C# derleme hataları oluşturmak mümkündür Q# .

#### <a name="simulation"></a>Benzetim

- Quantum Simulator, gereken doğrusal cebiri paralelleştirmek için OpenMP’yi kullanır. Varsayılan olarak, OpenMP kullanılabilir olan tüm donanım iş parçacıklarını kullanır. Böylelikle, gereken koordinasyon asıl işi küçülteceği için az sayıda qubit’i olan programlar sıkça yavaş çalışır. Bu, OMP_NUM_THREADS ortam değişkenini küçük bir sayıya ayarlayarak düzeltilebilir. Üstünkörü bir temel kural olarak, 1 iş parçacığı yaklaşık 4 qubit için uygundur ve her qubit başına bir tane ek iş parçacığı iyi bir sonuç verir. Ancak, bu kullandığınız algoritmaya yüksek oranda bağlıdır.

#### <a name="debugging"></a>Hata ayıklama

- F11 (Step in) Q# kodda çalışmıyor.
- Q#Bir kesme noktasında veya tek adımlı duraklamadan kodda kod vurgulama bazen yanlış olur. Doğru satır vurgulanır. Ancak, bazen vurgulama satırın yanlış sütunlarında başlayıp biter.

#### <a name="testing"></a>Test Etme

- Testler 64 bit modunda yürütülmelidir. Testleriniz BadImageFormatException hatasıyla başarısız olursa, Test menüsüne gidip Test Ayarları > Varsayılan İşlemci Mimarisi > X64’ü seçin.
- Bazı testlerin çalıştırılması uzun sürebilir (bilgisayarınıza bağlı olarak 5 dakikaya kadar çıkabilir). Bazıları yirmiden fazla qubit kullandığı için bu normaldir. En büyük testimiz 23 qubit üzerinde çalışır.

#### <a name="samples"></a>Örnekler

- Ortam değişkeni OMP_NUM_THREADS “1” olarak ayarlanmadığı sürece bazı küçük örnekler bazı makinelerde yavaş çalışabilir. “Simülasyon” bölümündeki sürüm notuna bakın.

#### <a name="libraries"></a>Kitaplıklar

- Farklı bağımsız değişkenlerde bir işleme geçirilen qubit’lerin ayrı öğe olduğuna yönelik örtük bir varsayım bulunur. Örneğin, tüm kitaplık (ve simülatör) işlemleri, denetlenen bir NOT’ye geçirilen iki qubit’in farklı qubit’ler olduğunu varsayar. Bu varsayımın ihlal edilmesi tahmin edilemeyen ve beklenmedik sonuçlara sebep olabilir. Bu, kuantum bilgisayar izleyici simülatörü kullanılarak test edilebilir.
- Microsoft.Quantum.Bind işlevi tüm durumlarda beklendiği gibi davranmayabilir.
- Temel alınan System.Math.Sign işlevinin her zaman bir tamsayı döndürmesine rağmen SignD işlevi Microsoft.Quantum.Extensions.Math ad alanında bir Int’den ziyade bir Double döndürür. Bu Double’ların tümünün belirli ikili gösterimleri olduğu için sonuçlar 1.0, -1.0 ve 0.0 ile karşılaştırılabilir.
