---
title: 'Q # programını çalıştırma yolları'
description: 'Q # programlarını çalıştırmanın farklı yollarına genel bakış. Komut satırından, Q # jupi Not defterleri ve Python veya bir .NET dilinde klasik ana bilgisayar programları.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
ms.openlocfilehash: 132c138d7c392ed2b4bd3d0079180b68adae4cfc
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85887763"
---
# <a name="ways-to-run-a-q-program"></a>Q # programını çalıştırma yolları

Hisse geliştirme setinin en büyük güçlerinden biri, platformlar ve geliştirme ortamları arasında esneklik sağlar.
Bununla birlikte, bu durum, yeni Q # kullanıcılarının, kendi kendini karıştırarak veya daha fazla bilgi edinmek için, bkz. [Install kılavuzunda](xref:microsoft.quantum.install)bulunan çok sayıda seçenek.
Bu sayfada, bir Q # programı çalıştırıldığında ne olduğunu açıkladık ve kullanıcıların bunu yapabilecekleri farklı yollarla karşılaştırıyoruz.

Birincil ayrım, Q # ' ın çalıştırılamadır:
- tek başına bir uygulama olarak, burada Q #, söz konusu tek dildir ve program doğrudan çağırılır. Bu kategoriye aslında iki yöntem yer almalıdır:
  - komut satırı arabirimi
  - Q# Jupyter Notebook’ları
- daha sonra programı çağıran ve döndürülen sonuçları daha sonra işlemek için Python veya .NET dilinde (ör. C# veya F #) yazılmış ek bir *ana bilgisayar programı*ile.

Bu işlemlerin ve bunların farklarının en iyi şekilde anlaşılması için, basit bir Q # programı ele alalım ve bunların yürütülme yollarını karşılaştırıyoruz.

## <a name="basic-q-program"></a>Temel Q # programı

Temel bir hisse, durumlardan biri olan $ \ket $ ve $ \tus$ gibi büyük bir üst konumda qubit hazırlamaktan ve {0} {1} Bu iki durumdan eşit olasılığa sahip olarak rastgele olacak.
Aslında bu işlem, [hisse rastgele numara Oluşturucu](xref:microsoft.quantum.quickstarts.qrng) hızlı başlangıcı 'nın çekirdeğisidir.

Q # içinde bu, aşağıdaki kod tarafından gerçekleştirilir:

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

Ancak, bu kod yalnızca Q # tarafından yürütülemez.
Bunun için, doğrudan ya da başka bir işlem tarafından---çağrıldığında yürütülen bir [işlemin](xref:microsoft.quantum.guide.basics#q-operations-and-functions)gövdesini yapması gerekir. Bu nedenle, aşağıdaki biçimde bir işlem yazabilirsiniz:
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
Bir işlem tanımladınız, ancak `MeasureSuperposition` hiçbir giriş yapılmaz ve [sonuç](xref:microsoft.quantum.guide.types)türünde bir değer döndürmez.

Bu sayfadaki örnekler yalnızca Q # *işlemleri*içerirken, tartıştığımız tüm kavramlar, q # *işlevlerine*eşit olarak değineceğiz ve bu nedenle bunlara toplu olarak *callables*olarak başvuracağız. Farkları, [s # temel kavramları: işlemler ve işlevler](xref:microsoft.quantum.guide.basics#q-operations-and-functions)ve bunları tanımlama hakkında daha fazla ayrıntı, [işlemler ve işlevlerde](xref:microsoft.quantum.guide.operationsfunctions)bulunabilir.

### <a name="callable-defined-in-a-q-file"></a>Bir Q # dosyasında tanımlanmış çağrılabilir

Çağrılabilir özelliği, Q # tarafından çağrılarak ve çalıştırılmıştı.
Ancak, tam bir Q # dosyası için daha fazla ek ekleme gerektirir `*.qs` .

Tüm Q # türleri ve callables (hem tanımladığınız hem de dile özgü olanlar), *ad alanları*içinde tanımlanır ve bu da başvurulabilen her bir tam ad sağlar.

Örneğin, [`H`](xref:microsoft.quantum.intrinsic.h) ve işlemleri, [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) ve [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) ad alanlarında ( [Q # standart kitaplıklarının](xref:microsoft.quantum.qsharplibintro)bir parçası) bulunur.
Bu nedenle, her zaman *tam* adlarıyla çağrılabilir, `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` ancak her zaman bunu yapmanız çok karışık koda yol açabilir.

Bunun yerine, `open` deyimler, yukarıdaki işlem gövdesinde yaptığımız gibi, callables 'e daha kısa toplu ile başvurulmalıdır.
Operasyonumuzu içeren tam Q # dosyası bu nedenle kendi ad boşluğumuzu tanımlamayı, işlediğimiz bu callabler için ad alanlarını açmayı ve sonra işleminizi içerir:

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> Ayrıca, iki ad alanındaki çağrılabilir/tür adları çakışıyorsa yararlı olabilecek ad alanları açıldıklarında da *diğer* ad olabilir.
> Örneğin, `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` Yukarıdaki ' ı kullanabilir ve ardından `H` aracılığıyla çağırabilirsiniz `NamespaceWithH.H(<qubit>)` .

> [!NOTE]
> Tüm bu tek istisna, [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) her zaman otomatik olarak açılan bir ad alanıdır.
> Bu nedenle, callables, [`Length`](xref:microsoft.quantum.core.length) her zaman doğrudan kullanılabilir.

### <a name="execution-on-target-machines"></a>Hedef makinelerde yürütme

Artık bir Q # programının genel yürütme modeli açık hale gelir.

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

İlk olarak, yürütülecek özel çağrılabilir, aynı ad alanında tanımlanan diğer tüm callables ve türlerine erişebilir.
Ayrıca, bunlara herhangi bir [Q # kitaplığı](xref:microsoft.quantum.libraries)'ndan erişin, ancak bunların tam adlarıyla veya yukarıda açıklanan deyimlerin kullanımı aracılığıyla başvurulmalıdır `open` .

Çağrılabilir kendisi bir *[hedef makinede](xref:microsoft.quantum.machines)* yürütülür.
Bu tür hedef makineler gerçek hisse donanımı veya QDK 'nin bir parçası olarak kullanılabilir birden çok simülatörleri olabilir.
Burada, bizim için en faydalı hedef makine, [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator) `QuantumSimulator` bir gürültü ücretsiz hisse bilgisayarında yürütülene gibi programın davranışını hesaplayan tam durum simülatörü örneğidir.

Şimdiye kadar, belirli bir Q # çağrılabilir yürütüldüğünde ne olduğunu açıklıyoruz.
Q # ' ın tek başına bir uygulamada mı yoksa bir konak programı ile mi kullanıldığına bakılmaksızın, bu genel işlem daha fazla veya daha az---, bu nedenle QDK 'nin esnekliği de aynıdır.
Bu nedenle, hisse geliştirme paketine çağrı yapmak için farklı yollar arasındaki farklılıklar, kendileri için Q # çağrılabilir olarak *nasıl* çağrıldığına ve sonuçların ne şekilde döndürüldüğünden ortaya çıkar.
Daha belirgin olarak, farklar ve etrafında 
1. Hangi Q çağrılabilir çağrılabilir çalıştırılacağını belirtir,
2. çağrılabilir olabilecek bağımsız değişkenlerin nasıl sağlandığı
3. üzerinde yürütüleceği hedef makineyi belirtme ve
4. sonuçların nasıl döndürüldüğü.

İlk olarak, komut satırından Q # tek başına uygulamasıyla bunun nasıl yapıldığını anladık ve Python ve C# ana bilgisayar programlarını kullanmaya devam ediyoruz.
İlk üçünün aksine, birincil işlevselliği yerel bir Q # dosyası etrafında ortalamadığından, en son Q # jupi Not defterlerinin tek başına uygulamasını ayırdık.

> [!NOTE]
> Bu örneklerde açıklanmadığımızda, yürütme yöntemleriyle ilgili bir genel durumda, Q # programının içinden yazdırılan tüm iletiler ( [`Message`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) Örneğin, veya gibi), her zaman ilgili konsola yazdırılır.

## <a name="q-from-the-command-line"></a>Q # komut satırından
Q # programlarını yazmaya başlamanın en kolay yollarından biri, ayrı dosyalar ve ikinci bir dilin tamamen kaygılanmasından kaçınmaktır.
Visual Studio Code veya Visual Studio 'Yu QDK uzantısıyla kullanmak, yalnızca tek bir Q # dosyasından Q # callables çalıştıran sorunsuz bir iş akışına olanak sağlar.

Bunun için, son olarak programın yürütmesini şunu girerek çağıracağız
```dotnetcli
dotnet run
```
komut satırında.
En basit iş akışı, terminalin Dizin konumunun, VS Code ' deki tümleşik Terminal kullanılarak, Q # dosyası düzenlemeyle birlikte kolayca işlenebilen Q # dosyası ile aynı olduğu durumlarda kullanılır.
Ancak, [ `dotnet run` komut](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) çok sayıda seçenek kabul eder ve ayrıca, aynı zamanda `--project <PATH>` Q # dosyasının konumuyla birlikte, program farklı bir konumdan da çalıştırılabilir.


### <a name="add-entry-point-to-q-file"></a>Q # dosyasına giriş noktası ekle

Çoğu Q # dosyası birden fazla çağrılabilir içerir, bu yüzden doğal olarak, komut sağlamamız durumunda derleyicinin *hangi* çağrılabilir yürütme yapacağını bilmesini sağlamamız gerekir `dotnet run` .
Bu, Q # dosyasının kendisinde basit bir değişiklik ile yapılır: 
    - `@EntryPoint()`çağrılabilir öğesinden hemen önce gelen bir satır ekleyin.

Yukarıdaki dosya bundan böyle olur
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

Şimdi, `dotnet run` komut satırından bir çağrısı `MeasureSuperposition` çalıştırılmakta ve döndürülen değer daha sonra doğrudan terminale yazdırılır.
Bu nedenle, ya da `One` yazdırılmış görürsünüz `Zero` . 

Aşağıda, daha fazla callabaldığınıza bakılmaksızın yalnızca `MeasureSuperposition` çalıştırılacağını unutmayın.
Buna ek olarak, çağrılabilir bir sorun değildir. Bu, çağrılabilir bir [belge açıklamalarını](xref:microsoft.quantum.guide.filestructure#documentation-comments) kendi bildiriminden önce içeriyorsa, `@EntryPoint()` öznitelik üzerine basitçe eklenebilir.

### <a name="callable-arguments"></a>Çağrılabilir bağımsız değişkenler

Şimdiye kadar, yalnızca giriş içermeyen bir işlem kabul ediyoruz.
Benzer bir işlem gerçekleştirmek istediğinizi varsayalım, ancak birden fazla qubit üzerinde---bağımsız değişken olarak sunulan sayı.
Bu tür bir işlem şöyle yazılabilir
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
döndürülen değer ölçüm sonuçlarının bir dizisidir.
Ve [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) [`ForEach`](xref:microsoft.quantum.arrays.foreach) ad alanlarında olduğunu ve [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) `open` her biri için ek deyimler kullanılmasını unutmayın.

`@EntryPoint()`Özniteliği bu yeni işlemden önce taşıdığımızda (bir dosyada yalnızca bir satır olabilir), çalıştırmayı denemek yalnızca `dotnet run` ek komut satırı seçeneklerinin gerekli olduğunu ve bunları nasıl ifade ettiğine ilişkin bir hata mesajı sonucu olarak sonuçlanır.

Komut satırı için genel biçim aslında olur `dotnet run [options]` ve çağrılabilir bağımsız değişkenler burada sağlanır.
Bu durumda, bağımsız değişkeni `n` eksik olur ve seçeneğini sağlamaları gerektiğini gösterir `-n <n>` . `MeasureSuperpositionArray` `n=4` Bu nedenle, qubit 'i çalıştırmak için

```dotnetcli
dotnet run -n 4
```

aşağıdakine benzer bir çıktı oluşturma

```output
[Zero,One,One,One]
```

Bu kurs birden çok bağımsız değişkene genişletilir.

> [!NOTE]
> ' Da tanımlanan bağımsız değişken adları `camelCase` , derleyici tarafından, Q # girişi olarak kabul edilmesi için biraz değişmiş. Örneğin, yerine `n` Yukarıdaki adı kullandık, `numQubits` Bu giriş, komut satırında yerine kullanılarak sağlanacaktır `--num-qubits 4` `-n 4` .

Hata iletisi ayrıca, hedef makinenin nasıl değiştirileceği dahil olmak üzere kullanılabilecek diğer seçenekleri de sağlar.

### <a name="different-target-machines"></a>Farklı hedef makineler

İşlemlerimizin çıkışları gerçek qubit üzerinde eylemin beklenen sonuçları olduğundan, komut satırından varsayılan hedef makinenin tam durum çıkarkileri simülatörü `QuantumSimulator` ,
Ancak, callables ' i `--simulator` (veya toplu) belirli bir hedef makinede çalıştırmayı söyleyebilirsiniz `-s` .

Örneğin, şunu üzerinde çalıştırabiliriz [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

Yazdırılan çıkış daha sonra

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

Bu ölçümlerin neleri belirtebileceği hakkında ayrıntılı bilgi için bkz. [kaynak tahmini: raporlanan ölçümler](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).

### <a name="command-line-execution-summary"></a>Komut satırı yürütme Özeti
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-q-dotnet-run-options"></a>Q olmayan `dotnet run` Seçenekler

Bu seçenekte kısaca bahsedildiği gibi `--project` , [ `dotnet run` komut](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) , Q # çağrılabilir bağımsız değişkenleriyle ilgisi olmayan seçenekleri de kabul eder.
Her iki tür seçeneği de sağladıysanız, `dotnet` önce özel seçeneklerin önce sağlanması ve ardından bir delil `--` ve ardından Q # 'a özgü seçenekleri sağlaması gerekir.
Örneğin, yukarıdaki işlem için bir sayı ile birlikte bir yolu belirtir, aracılığıyla yürütülür `dotnet run --project <PATH> -- -n <n>` .

## <a name="q-with-host-programs"></a>Ana bilgisayar programları ile Q #

Q # dosyası birlikte, doğrudan komut satırından bir işlem veya işlev çağırma alternatifi, bir *konak programını* başka bir klasik dilde kullanmaktır. Özellikle, bu, Python veya C# ya da F # gibi bir .NET diliyle yapılabilir (breçların sake 'ı için burada yalnızca c# ayrıntı alınacaktır).
Birlikte çalışabilirliği etkinleştirmek için biraz daha fazla kurulum gerekir, ancak bu Ayrıntılar [yükleme kılavuzlarında](xref:microsoft.quantum.install)bulunabilir.

Bir Nutshell 'de, durum artık `*.py` `*.cs` Q # dosyası ile aynı konumdaki bir ana bilgisayar program dosyası (ör. veya) içeriyor.
Şimdi çalıştırılan *ana bilgisayar* programı ve yürütme işlemi sırasında, q # dosyasındaki belirli Q # işlemlerini ve işlevleri çağırabilir.
Birlikte çalışabilirliğin çekirdeği,, çağrılabilmesi için Q # dosyasının içeriğini ana bilgisayar programına erişilebilir hale getiren Q # derleyicisini temel alır.

Ana bilgisayar programı kullanmanın başlıca avantajlarından biri, Q # programı tarafından döndürülen klasik verilerin daha sonra konak dilinde işlenebilmesi olabilir.
Bu, bazı gelişmiş veri işlemeden (örneğin, Q # ' da dahili olarak gerçekleştirilemediği bir şey) ve ardından bu sonuçlara göre daha fazla soru-cevap veya Q # sonuçlarını çizmek kadar basit bir şey olabilir.

Genel düzen burada gösterilmektedir ve aşağıda Python ve C# için özel uygulamalar tartışıyoruz. F # ana bilgisayar programını kullanan bir örnek, [.net birlikte çalışabilirlik örneklerinde](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)bulunabilir.

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> `@EntryPoint()`Q # komut satırı uygulamaları için kullanılan öznitelik konak programlarıyla birlikte kullanılamaz.
> Bir ana bilgisayar tarafından çağrılan Q # dosyasında varsa bir hata oluşur. 

Farklı ana bilgisayar programlarıyla çalışmak için, bir Q # dosyasında gerekli değişiklik yoktur `*.qs` .
Aşağıdaki konak program uygulamalarının hepsi aynı Q # dosyasıyla çalışır:

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

İlgilendiğiniz ana bilgisayar dilinize karşılık gelen sekmeyi seçin.

### <a name="python"></a>[Python](#tab/tabid-python)
Bir Python ana bilgisayar programı şu şekilde oluşturulur:
1. `qsharp`Q # birlikte çalışabilirlik için modül yükleyicisini kaydeden modülünü içeri aktarın. 
    Bu, Q # ad alanlarının Python modülleri olarak görünmesine izin verir, buradan "içeri aktarabilir".
    Teknik olarak içeri aktarılan ve bunlara çağırmaya izin veren Python saplamalarının kendisine Teknik olarak olmadığını unutmayın.
    Bunlar daha sonra Python sınıflarının nesneleri olarak davranır, bu durumda, yürütme için işlemi gönderecek hedef makineleri belirtmek için yöntemler kullanıyoruz.

2. Bu durumda---doğrudan çağıracağız Bu Q # callables 'i içeri aktarın `MeasureSuperposition` ve `MeasureSuperpositionArray` .
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    `qsharp`Modül içeri aktarılmışsa Ayrıca, doğrudan Q # kitaplığı ad alanlarından callables 'yi içeri aktarabilirsiniz.

3. Diğer herhangi bir Python kodu arasında, artık bu callabları belirli hedef makinelere çağırabilir ve geri dönüşlerini, daha fazla kullanım için (bir değer döndürdüler) değişkenlere atayabilirsiniz.

#### <a name="specifying-target-machines"></a>Hedef makineleri belirtme
Belirli bir hedef makinede çalıştırılacak bir işlemin çağrılması, içeri aktarılan nesnede farklı Python yöntemleri aracılığıyla yapılır.
Örneğin, `.simulate(<args>)` `QuantumSimulator` işlemini çalıştırmak için öğesini kullanır, ancak `.estimate_resources(<args>)` bunu yapar `ResourcesEstimator` .

#### <a name="passing-inputs-to-q"></a>Girdileri Q 'a geçirme\#
Q # çağrılabilir bağımsız değişkenleri, anahtar sözcüğünün Q # çağrılabilir tanımında bağımsız değişken adı olduğu anahtar sözcük bağımsız değişkeni biçiminde sağlanmalıdır.
Yani, `MeasureSuperpositionArray.simulate(n=4)` geçerlidir, ancak `MeasureSuperpositionArray.simulate(4)` bir hata oluşturur.

Bu nedenle, Python ana bilgisayar programı 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

aşağıdakine benzer bir çıktı oluşur:

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[C#](#tab/tabid-csharp)

C# ana bilgisayar programında birden çok bileşen vardır ve bunlar, c# üzerinde oluşturulan simülatörleri gibi bazı QDK bileşenleriyle çok daha yakından çalışmaktadır.

Q # derleyicisi, Q # dosyanızdaki Q # ad alanından bir equivalently adlı C# ad alanı oluşturarak burada işe yarar.
Daha sonra, her Q # callables veya içinde tanımlanan türler için bir equivalently adlandırılmış C# sınıfı oluşturur.

İlk olarak, ana programımızda `using` , `open` Q # dosyanızdaki deyimler için kabaca bir şekilde olan deyimlerle kullanılabilen tüm sınıfları sunuyoruz:

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

Daha sonra C# ad boşluğumuzu, diğer birkaç bit ve parçadan (örneğin, Q # callables için bilgi işlem bağımsız değişkenleri) bildiririz.
İkinci durumda gerekli değildir, ancak bu tür bir örnek [.net birlikte çalışabilirlik örneğinde](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)bulunabilir.

#### <a name="target-machines"></a>Hedef makineler

Q # ' a geri döndüğünüzde, operasyonlarımızı yürütediğimiz hedef makinenin bir örneğini oluşturmamız gerekir.

```csharp
            using var sim = new QuantumSimulator();
```

Diğer hedef makinelerin kullanılması, farklı bir örnek oluşturmak kadar basittir, ancak bunu yapmanın ve döndürmesinin işlem biçimi biraz farklı olabilir.
Kısaltma için, şu an için ' i kullanıma sunuyoruz [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) ve aşağıdakileri dahil ediyoruz [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).

Q # işlemlerinden oluşturulan her C# sınıfının `Run` , hedef makine örneği olması gereken ilk bağımsız değişkeni olan bir yöntemi vardır.
Bu nedenle, `MeasureSuperposition` üzerinde çalıştırmak için `QuantumSimulator` kullanırız `MeasureSuperposition.Run(sim)` .
Döndürülen sonuçlar daha sonra C# dilinde değişkenlere atanabilir:

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> `Run`Bu, gerçek hisse donanımı için durum olacağı için zaman uyumsuz olarak yürütülür ve bu nedenle `await` anahtar sözcüğü, görev tamamlanana kadar daha fazla yürütmeyi engeller.

Q # çağrılabilir değeri herhangi bir dönüşe sahip değilse (örneğin, dönüş türüne sahipse `Unit` ), yürütme yine de bir değişkene atamadan aynı şekilde yapılabilir.
Bu durumda, tüm satır yalnızca 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>Arguments

İstenen Q # çağrılabilir bağımsız değişkenleri, hedef makineyi afleyici ek bağımsız değişkenler olarak geçirilir.
Bu nedenle, `MeasureSuperpositionArray` `n=4` qubits 'in sonuçları aracılığıyla getirilir 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

Böylece tam bir C# ana bilgisayar programı şöyle görünebilir

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

C# dosyasının konumunda, ana bilgisayar programı komut satırından şunu girerek çalıştırılabilir:
```dotnetcli
dotnet run
```
Bu durumda, şuna benzer şekilde konsola yazılan çıktıyı görürsünüz: 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> Derleyicinin ad alanları ile birlikte çalışabilirliği nedeniyle, bildirim olmadan Q # callablımlarımızı de kullanılabilir hale getirir `using NamespaceName;` ve C# ad alanı başlığını bununla eşleştirmeniz yeterlidir.
> Diğer bir deyişle, `namespace host` ile değiştirin `namespace NamespaceName` .

#### <a name="including-the-resources-estimator"></a>Kaynak tahmin aracı dahil

, [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) Çıktıyı almak için biraz farklı bir uygulama gerektirir.

İlk olarak, bunları bir ifadesiyle bir değişken olarak Örneklemek yerine `using` (ile yaptığımız gibi `QuantumSimulator` ), ile sınıfın nesnelerini doğrudan örnekliyoruz

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

Tek bir hedef Benzetici yerine birden çok Q # işlemi tarafından kullanılacak şekilde, her biri için bir tane örnekliyoruz. Bunun nedeni, nesnelerin kendisi hedef makineler olarak kullanıldığında değiştirilmektedir ve sonuçları daha sonra sınıf yöntemiyle elde edilebilir `.ToTSV()` .

Kaynakları kaynak estimators üzerinde çalıştırmak için şunu kullanıyoruz

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
ardından sonuçları ve ile sekmeyle ayrılmış değerler (TSV) olarak getirin `estimatorSingleQ.ToTSV()` `estimatorMultiQ.ToTSV()` .

Bu nedenle, hem hem de kullanan tam bir C# ana bilgisayar `QuantumSimulator` programı `ResourcesEstimator` şu biçimde olabilir:

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


aşağıdakine benzer bir çıktı verecek

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="q-jupyter-notebooks"></a>Q# Jupyter Notebook’ları
S # Jupyter Not defterleri, tek bir not defterinde soru, Not ve diğer içeriklerden oluşan---Q # callables 'i tanımlamanızı, derlemenize ve çalıştırmanıza olanak tanıyan IQ # çekirdeğini kullanır.
Diğer bir deyişle, Q # dosyalarının içeriğini içeri ve dışarı aktarmak mümkün olsa `*.qs` da, bunlar yürütme modelinde gerekli değildir.

Burada, yukarıda tanımlanan Q # işlemlerini nasıl çalıştıracağınızı ayrıntılarız, ancak q # Jupyıter not defterlerini kullanmaya yönelik daha geniş bir giriş, [q # ve jupi not defterlerine giriş olarak](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)sunulmaktadır.

### <a name="defining-operations"></a>İşlemleri tanımlama

Bir Q # Jupyter Notebook, bir q # dosyasının ad alanının içinden yaptığımız gibi Q # kodunu girersiniz.

Bu nedenle, ilgili ad alanları için deyimlerle [Q # standart kitaplıklarından](xref:microsoft.quantum.qsharplibintro) callables 'e erişimi etkinleştirebiliriz `open` .
Bu tür bir deyime sahip bir hücreyi çalıştırırken, bu ad alanlarından alınan tanımlar çalışma alanı boyunca kullanılabilir.

> [!NOTE]
> [Microsoft. hisse. iç](xref:microsoft.quantum.intrinsic) ve [Microsoft. hisse. Canon](xref:microsoft.quantum.canon) (örn.) ile Callables [`H`](xref:microsoft.quantum.intrinsic.h) [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) , Q # jupi Not defterlerindeki hücrelerde tanımlanan işlemler için otomatik olarak kullanılabilir.
> Ancak, bu, dış Q # kaynak dosyalarından alınan kod için (örneğin, [Q # ve jupi not defterlerine giriş olarak](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)gösterilen bir işlem) doğru değildir. 
> 

Benzer şekilde, tanımlama işlemleri yalnızca Q # kodu yazmak ve hücreyi çalıştırmak için gereklidir.

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

Daha sonra çıktı bu işlemleri listeler, daha sonra gelecekteki hücrelerden çağrılabilir.

### <a name="target-machines"></a>Hedef makineler

Belirli hedef makinelerde işlem çalıştırma işlevselliği [IQ # Magic komutları](xref:microsoft.quantum.guide.quickref.iqsharp)aracılığıyla sağlanır.
Örneğin, `%simulate` `QuantumSimulator` öğesini kullanır ve şunları `%estimate` kullanır `ResourcesEstimator` :

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a>İşlevlere ve işlemlere giriş geçirme

Şu anda yürütme Magic komutları yalnızca bağımsız değişken içermeyen işlemlerle birlikte kullanılabilir. Bu nedenle, çalıştırmak için `MeasureSuperpositionArray` bir "sarmalayıcı" işlemi tanımlamamız gerekir ve bu işlemden sonra işlemi bağımsız değişkenlerle çağırır:

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

Bu işlem, `%estimate` ve diğer yürütme komutlarıyla benzer şekilde kullanılabilir.
