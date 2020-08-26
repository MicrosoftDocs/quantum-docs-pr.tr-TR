---
title: Program çalıştırma yolları Q#
description: Programları çalıştırmanın farklı yollarına genel bakış Q# . Komut isteminden, Q# jupi Not defterleri ve Python veya bir .net dilinde klasik ana bilgisayar programları.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: e44a366b7eea133499beb44dbb338a02174c0073
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863144"
---
# <a name="ways-to-run-a-no-locq-program"></a>Program çalıştırma yolları Q#

Hisse geliştirme setinin en büyük güçlerinden biri, platformlar ve geliştirme ortamları arasında esneklik sağlar.
Bununla birlikte, bu durum, yeni Q# kullanıcıların kendi kendini karıştırarak veya daha fazla bilgi edinmek için, bkz. [Install kılavuzunda](xref:microsoft.quantum.install)bulunan çok sayıda seçenek.
Bu sayfada, bir program çalıştırıldığında ne olduğunu açıkladık Q# ve kullanıcıların bunu yapabilecekleri farklı yollarla karşılaştırıyoruz.

Birincil ayrım, çalıştırılabilir bir değer olabilir Q# :
- tek başına bir uygulama olarak, Q# söz konusu tek dildir ve program doğrudan çağırılır. Bu kategoriye aslında iki yöntem yer almalıdır:
  - komut satırı arabirimi
  - Q# Jupyıter Not defterleri
- daha sonra programı çağıran ve döndürülen sonuçları daha sonra işlemek için Python veya .NET dilinde (ör. C# veya F #) yazılmış ek bir *ana bilgisayar programı*ile.

Bu işlemlerin ve bunların farklarının en iyi şekilde anlaşılması için, basit bir Q# programı ele alalım ve bunların yürütülme yollarını karşılaştırıyoruz.

## <a name="basic-no-locq-program"></a>Temel Q# Program

Temel bir hisse, durumlardan biri olan $ \ket $ ve $ \tus$ gibi büyük bir üst konumda qubit hazırlamaktan ve {0} {1} Bu iki durumdan eşit olasılığa sahip olarak rastgele olacak.
Aslında bu işlem, [hisse rastgele numara Oluşturucu](xref:microsoft.quantum.quickstarts.qrng) hızlı başlangıcı 'nın çekirdeğisidir.

Q#' De, bu, aşağıdaki kod tarafından gerçekleştirilir:

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

Ancak, bu kod yalnızca tarafından yürütülemez Q# .
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

Bu sayfadaki örnekler yalnızca Q# *işlemlerden*oluşurken, tartıştığımız kavramların hepsi işlevleri ile aynı şekilde ele alınacaktır Q# *functions*. bu nedenle, bunlara toplu olarak *callables*olarak başvuracağız. Bunların farklılıkları temel alınarak açıklanmaktadır [ Q# : işlemler ve işlevler](xref:microsoft.quantum.guide.basics#q-operations-and-functions)ve bunların tanımlanması hakkında daha fazla ayrıntı, [işlemler ve işlevlerde](xref:microsoft.quantum.guide.operationsfunctions)bulunabilir.

### <a name="callable-defined-in-a-no-locq-file"></a>Bir dosyada tanımlanmış çağrılabilir Q#

Çağrılabilir, tam olarak aranan ve tarafından çalıştırılan şeydir Q# .
Ancak, tam bir dosyayı oluşturacak birkaç ekleme daha vardır `*.qs` Q# .

Tüm Q# türler ve callables (hem tanımladığınız hem de dile özgü olan) *ad alanları*içinde tanımlanır ve bu, daha sonra başvurulabilen her bir tam adı sağlar.

Örneğin, [`H`](xref:microsoft.quantum.intrinsic.h) ve işlemleri, [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) ve [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) ad alanlarında ( [ Q# standart kitaplıkların](xref:microsoft.quantum.qsharplibintro)bir parçası) bulunur.
Bu nedenle, her zaman *tam* adlarıyla çağrılabilir, `Microsoft.Quantum.Intrinsic.H(<qubit>)` `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` ancak her zaman bunu yapmanız çok karışık koda yol açabilir.

Bunun yerine, `open` deyimler, yukarıdaki işlem gövdesinde yaptığımız gibi, callables 'e daha kısa toplu ile başvurulmalıdır.
Q#Bu nedenle, işlemizi içeren tam dosya, kendi ad alanımızın tanımlanmasından, işlediğimiz bu callabların ad alanlarını açmaya ve sonra işleyimize neden olacak:

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

Artık bir programın genel yürütme modeli Q# açık hale gelir.

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

İlk olarak, yürütülecek özel çağrılabilir, aynı ad alanında tanımlanan diğer tüm callables ve türlerine erişebilir.
Ayrıca, [ Q# kütüphanelerin](xref:microsoft.quantum.libraries)herhangi birinden bunlara erişir, ancak bunların tam adlarıyla veya yukarıda açıklanan deyimlerin kullanımı aracılığıyla başvurulmalıdır `open` .

Çağrılabilir kendisi bir *[hedef makinede](xref:microsoft.quantum.machines)* yürütülür.
Bu tür hedef makineler gerçek hisse donanımı veya QDK 'nin bir parçası olarak kullanılabilir birden çok simülatörleri olabilir.
Burada, bizim için en faydalı hedef makine, [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator) `QuantumSimulator` bir gürültü ücretsiz hisse bilgisayarında yürütülene gibi programın davranışını hesaplayan tam durum simülatörü örneğidir.

Şimdiye kadar, belirli bir çağrılabilir yürütüldüğünde ne olduğunu açıklıyoruz Q# .
Q#Tek başına bir uygulamada veya bir konak programıyla kullanılıp kullanılmadığına bakılmaksızın, bu genel işlem daha fazla veya daha az---, bu nedenle QDK 'nin esnekliği de aynıdır.
Bu nedenle, hisse alma geliştirme paketine çağırmanın farklı yolları arasındaki farklılıklar, kendilerini çağrılabilir şekilde *nasıl* Q# çağrıldığına ve sonuçların ne şekilde döndürüldüğünden ortaya çıkar.
Daha belirgin olarak, farklar ve etrafında 
1. Hangi Q# çağrılabilir yürütülür olduğunu belirtir,
2. çağrılabilir olabilecek bağımsız değişkenlerin nasıl sağlandığı
3. üzerinde yürütüleceği hedef makineyi belirtme ve
4. sonuçların nasıl döndürüldüğü.

İlk olarak, komut isteminden tek başına uygulama ile bunun nasıl yapıldığını anladık Q# ve Python ve C# ana bilgisayar programlarını kullanmaya devam ediyoruz.
Q#İlk üçünün aksine, birincil işlevselliği yerel bir dosya etrafında ortalamadığından, en son jupi Not defterlerinin tek başına uygulamasını ayırdık Q# .

> [!NOTE]
> Bu örneklerde anlamadığımızda, yürütme yöntemleriyle ilgili bir genel durumda, program içinden yazdırılan tüm iletiler Q# ( [`Message`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) Örneğin, veya) her zaman ilgili konsola yazdırılır.

## <a name="no-locq-from-the-command-prompt"></a>Q# komut isteminden
Programları yazmaya başlamanın en kolay yollarından biri Q# , ayrı dosyalar ve ikinci bir dilin tamamen kaygılanmasından kaçınmaktır.
Visual Studio Code veya Visual Studio 'Yu QDK uzantısıyla kullanmak, Q# tek bir dosyadan callables çalıştırdığımız sorunsuz bir iş akışına olanak sağlar Q# .

Bunun için, son olarak programın yürütmesini şunu girerek çağıracağız
```dotnetcli
dotnet run
```
komut isteminde.
En basit iş akışı, terminalin Dizin konumunun dosyayla aynı olduğu Q# , Q# Örneğin vs Code ' deki tümleşik Terminal kullanılarak dosya düzenlemeyle birlikte kolayca işlenebilen bir dosyadır.
Ancak, [ `dotnet run` komut](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) çok sayıda seçenek kabul eder ve yalnızca `--project <PATH>` dosyanın konumuyla birlikte sağlanarak program farklı bir konumdan da çalıştırılabilir Q# .


### <a name="add-entry-point-to-no-locq-file"></a>Dosyaya giriş noktası Ekle Q#

Çoğu Q# dosya birden fazla çağrılabilir, *Bu* yüzden doğal olarak, komut sağlamamız durumunda derleyicinin hangi çağrılabilir yürütme yapacağını bilmesini sağlamamız gerekir `dotnet run` .
Bu, dosyanın kendisinde basit bir değişiklik ile yapılır Q# : 
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

Şimdi, `dotnet run` komut isteminden bir çağrısı `MeasureSuperposition` çalıştırılmakta ve döndürülen değer daha sonra doğrudan terminale yazdırılır.
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

`@EntryPoint()`Özniteliği bu yeni işlemden önce (örneğin, bir dosyada yalnızca bir satır olabilir) taşıdığımızda, çalıştırmayı denemek yalnızca bir `dotnet run` hata mesajı ile sonuçlanmaya, hangi ek komut satırı seçeneklerinin gerekli olduğunu ve bunları nasıl ifade ettiğine ilişkin bir hata iletisiyle sonuçlanır.

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
> ' Da tanımlanan bağımsız değişken adları `camelCase` , giriş olarak kabul edilmesi için derleyici tarafından biraz değişiklik gösterebilir Q# . Örneğin, yerine `n` Yukarıdaki adı kullandık, `numQubits` Bu giriş, komut satırında yerine kullanılarak sağlanacaktır `--num-qubits 4` `-n 4` .

Hata iletisi ayrıca, hedef makinenin nasıl değiştirileceği dahil olmak üzere kullanılabilecek diğer seçenekleri de sağlar.

### <a name="different-target-machines"></a>Farklı hedef makineler

İşlemlerimizin çıkışları gerçek qubit üzerinde eylemin beklenen sonuçları olduğundan, komut satırından varsayılan hedef makinenin tam durum hisse benzeticileri olduğunu temizler `QuantumSimulator` .
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

### <a name="non-no-locq-dotnet-run-options"></a>Seçenek olmayanlar Q# `dotnet run`

Bu seçenekte kısaca bahsedilen gibi `--project` , [ `dotnet run` komut](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) çağrılabilir bağımsız değişkenlerle ilgisi olmayan seçenekleri de kabul eder Q# .
Her iki tür seçeneği de sağladıysanız, `dotnet` önce özel seçenekler önce, sonra da bir `--` Q# delil ve ardından özel seçenekler sağlanmalıdır.
Örneğin, yukarıdaki işlem için bir sayı ile birlikte bir yolu belirtir, aracılığıyla yürütülür `dotnet run --project <PATH> -- -n <n>` .

## <a name="no-locq-with-host-programs"></a>Q# Konak programları ile

Dosya ile birlikte Q# , doğrudan komut isteminden bir işlem veya işlev çağırma alternatifi, bir *konak programını* başka bir klasik dilde kullanmaktır. Özellikle, bu, Python veya C# ya da F # gibi bir .NET diliyle yapılabilir (breçların sake 'ı için burada yalnızca c# ayrıntı alınacaktır).
Birlikte çalışabilirliği etkinleştirmek için biraz daha fazla kurulum gerekir, ancak bu Ayrıntılar [yükleme kılavuzlarında](xref:microsoft.quantum.install)bulunabilir.

Bir Nutshell 'de, durum artık, `*.py` `*.cs` dosya ile aynı konumda bir ana bilgisayar program dosyası (ör. veya) içeriyor Q# .
Şimdi çalıştırılan *ana bilgisayar* programıdır ve yürütme sırasında, Q# dosyadaki belirli işlemleri ve işlevleri çağırabilir Q# .
Birlikte çalışabilirlik çekirdeği, Q# Q# bir dosyanın içeriğini ana bilgisayar programına erişilebilir hale getiren derleyiciye dayanır, böylece çağrılabilir.

Ana bilgisayar programı kullanmanın başlıca avantajlarından biri, program tarafından döndürülen klasik verilerin Q# daha sonra konak dilinde daha fazla işlenebilir olması olabilir.
Bu, bazı gelişmiş veri işlemeden (örneğin, içinde yerleşik olarak gerçekleştirilemediği bir şey Q# ) ve ardından Q# Bu sonuçlara göre daha fazla eylem veya sonuçları çizdirme kadar basit bir şey olabilir Q# .

Genel düzen burada gösterilmektedir ve aşağıda Python ve C# için özel uygulamalar tartışıyoruz. F # ana bilgisayar programını kullanan bir örnek, [.net birlikte çalışabilirlik örneklerinde](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)bulunabilir.

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> `@EntryPoint()`Uygulamalar için kullanılan öznitelik Q# konak programlarıyla kullanılamaz.
> Q#Bir ana bilgisayar tarafından çağrılan dosyada mevcutsa bir hata oluşur. 

Farklı ana bilgisayar programlarıyla çalışmak için, bir dosya için gerekli değişiklik yoktur `*.qs` Q# .
Aşağıdaki konak program uygulamalarının hepsi aynı Q# dosyayla çalışır:

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
1. Modül `qsharp` yükleyicisini birlikte çalışabilirlik için kaydeden modülünü içeri aktarın Q# . 
    Bu Q# , ad alanlarının Python modülleri olarak görünmesine izin verir ve bu da "içeri aktarabilir" Q# .
    Teknik olarak Q# , içeri aktarılan ve bunlara çağrı sağlayan Python saplamalarının kendilerine ait olduğunu unutmayın.
    Bunlar daha sonra Python sınıflarının nesneleri olarak davranır, bu durumda, yürütme için işlemi gönderecek hedef makineleri belirtmek için yöntemler kullanıyoruz.

2. Q#Bu durumda---doğrudan çağıracağız bu callables 'yi içeri aktarın `MeasureSuperposition` ve `MeasureSuperpositionArray` .
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    `qsharp`Modül içeri aktarılmışsa, ayrıca doğrudan kitaplık ad alanlarından callables 'yi içeri aktarabilirsiniz Q# .

3. Diğer herhangi bir Python kodu arasında, artık bu callabları belirli hedef makinelere çağırabilir ve geri dönüşlerini, daha fazla kullanım için (bir değer döndürdüler) değişkenlere atayabilirsiniz.

#### <a name="specifying-target-machines"></a>Hedef makineleri belirtme
Belirli bir hedef makinede çalıştırılacak bir işlemin çağrılması, içeri aktarılan nesnede farklı Python yöntemleri aracılığıyla yapılır.
Örneğin, `.simulate(<args>)` `QuantumSimulator` işlemini çalıştırmak için öğesini kullanır, ancak `.estimate_resources(<args>)` bunu yapar `ResourcesEstimator` .

#### <a name="passing-inputs-to-q"></a>Girdileri Q 'a geçirme\#
Çağrılabilir bağımsız değişkenleri Q# , anahtar sözcüğünün çağrılabilir tanımda bağımsız değişken adı olduğu anahtar sözcük bağımsız değişkeni biçiminde sağlanmalıdır Q# .
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

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a>Q#Diğer projelerden veya paketlerdeki kodu kullanma

Varsayılan olarak, `import qsharp` komut tüm `.qs` dosyaları geçerli klasöre yükler ve kendi Q# Işlemlerini ve işlevlerini Python betiği içinden kullanıma sunar.

Başka bir Q# klasörden kod yüklemek için [ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp/qsharp.projects.projects) , bir proje için bir dosyaya başvuru eklemek için kullanılabilir `.csproj` (yani Q# , başvuran bir proje `Microsoft.Quantum.Sdk` ).
Bu komut `.qs` , ve alt klasörlerini içeren klasördeki tüm dosyaları derler `.csproj` . Ayrıca, `PackageReference` ya da Q# Bu dosyanın üzerinden başvurulan projeler aracılığıyla başvurulan paketleri yinelemeli olarak yükler `ProjectReference` `.csproj` .

Örnek olarak, aşağıdaki Python kodu bir dış projeyi içeri aktarır ve geçerli klasöre göre yoluna başvurarak, işlemlerinden birini çağırır Q# :

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

Bu, aşağıdakine benzer bir çıktı ile sonuçlanır:

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

Kod içeren harici paketleri yüklemek için Q# [ `qsharp.packages` API](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages)'yi kullanın.

Q#Geçerli klasördeki kod dış projelere veya paketlere bağımlıysa, `import qsharp` Bağımlılıklar henüz yüklenmediği için çalışırken hatalarla karşılaşabilirsiniz.
Komut sırasında gerekli harici paketleri veya Q# projeleri yüklemek için `import qsharp` , Python betiğinin bulunduğu klasörde, başvuruda bulunan bir dosya bulunduğundan emin olun `.csproj` `Microsoft.Quantum.Sdk` . Bu durumda, `.csproj` özelliğini öğesine ekleyin `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` `<PropertyGroup>` . Bu, Q# `ProjectReference` `PackageReference` komutu sırasında ' de bulunan herhangi bir veya öğesini yinelemeli olarak yükleyemem talimatını verecektir `.csproj` `import qsharp` .

Örneğin, `.csproj` Q# paketi otomatik olarak yükleyemem neden olan basit bir dosya aşağıda verilmiştir `Microsoft.Quantum.Chemistry` :

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> Şu anda bu özel `<IQSharpLoadAutomatically>` özellik Python konakları için gereklidir, ancak gelecekte bu, `.csproj` Python betiği ile aynı klasörde bulunan bir dosya için varsayılan davranış haline gelebilir.

> [!NOTE]
> `<QsharpCompile>`' Deki ayarı, `.csproj` Python konakları tarafından yok sayılır ve `.qs` `.csproj` (alt klasörler dahil) klasöründeki tüm dosyalar yüklenir ve derlenir. `.csproj`Gelecekte ayarlar için destek sunulacaktır (daha fazla ayrıntı için bkz. [ıqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) ).


### <a name="c"></a>[C#](#tab/tabid-csharp)

C# ana bilgisayar programında birden çok bileşen vardır ve bunlar, c# üzerinde oluşturulan simülatörleri gibi bazı QDK bileşenleriyle çok daha yakından çalışmaktadır.

Q#Derleyici burada, dosyanızdaki ad alanından bir equivalently adlı C# ad alanı oluşturarak işe yarar Q# Q# .
Daha sonra, her bir Q# callables veya içinde tanımlanan türler için bir equivalently adlandırılmış C# sınıfı oluşturur.

İlk olarak, bir ana bilgisayar programımızda `using` , `open` bizim dosyanızdaki deyimlerde kabaca bir şekilde olan deyimlerle kullanılabilir olan tüm sınıfları sunuyoruz Q# :

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

Daha sonra C# ad boşluğumuzu, diğer birkaç bit ve parçadan (örneğin, callables için bilgi işlem bağımsız değişkenleri) bildiririz Q# .
İkinci durumda gerekli değildir, ancak bu tür bir örnek  [.net birlikte çalışabilirlik örneğinde](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)bulunabilir.

#### <a name="target-machines"></a>Hedef makineler

Uygulamasına geri döndüğünüzde Q# , üzerinde operasyonlarımızı yürütediğimiz her türlü hedef makinenin bir örneğini oluşturmamız gerekir.

```csharp
            using var sim = new QuantumSimulator();
```

Diğer hedef makinelerin kullanılması, farklı bir örnek oluşturmak kadar basittir, ancak bunu yapmanın ve döndürmesinin işlem biçimi biraz farklı olabilir.
Kısaltma için, şu an için ' i kullanıma sunuyoruz [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) ve aşağıdakileri dahil ediyoruz [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [below](#including-the-resources-estimator).

İşlemlerden oluşturulan her C# sınıfının Q# `Run` , hedef makine örneği olması gereken ilk bağımsız değişkeni olan bir yöntemi vardır.
Bu nedenle, `MeasureSuperposition` üzerinde çalıştırmak için `QuantumSimulator` kullanırız `MeasureSuperposition.Run(sim)` .
Döndürülen sonuçlar daha sonra C# dilinde değişkenlere atanabilir:

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> `Run`Bu, gerçek hisse donanımı için durum olacağı için zaman uyumsuz olarak yürütülür ve bu nedenle `await` anahtar sözcüğü, görev tamamlanana kadar daha fazla yürütmeyi engeller.

Q#Çağrılabilir bir dönüşe sahip değilse (örneğin, dönüş türüne sahipse `Unit` ), yürütme yine de bir değişkene atamadan aynı şekilde yapılabilir.
Bu durumda, tüm satır yalnızca 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>Arguments

Çağrılabilir olan bağımsız değişkenler, Q# hedef makineyi Afren ek bağımsız değişkenler olarak geçirilir.
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

C# dosyasının konumunda, ana bilgisayar programı komut isteminden şunu girerek çalıştırılabilir:
```dotnetcli
dotnet run
```
Bu durumda, şuna benzer şekilde konsola yazılan çıktıyı görürsünüz: 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> Derleyicinin ad alanları ile birlikte çalışabilirliğine bağlı olarak, ayrıca Q# ıvgımlerimizi `using NamespaceName;` deyimsiz olarak kullanabilir ve C# ad alanı başlığını bununla eşleştirmeniz yeterlidir.
> Diğer bir deyişle, `namespace host` ile değiştirin `namespace NamespaceName` .

#### <a name="including-the-resources-estimator"></a>Kaynak tahmin aracı dahil

, [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) Çıktıyı almak için biraz farklı bir uygulama gerektirir.

İlk olarak, bunları bir ifadesiyle bir değişken olarak Örneklemek yerine `using` (ile yaptığımız gibi `QuantumSimulator` ), ile sınıfın nesnelerini doğrudan örnekliyoruz

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

Tek bir hedef simülatörü yerine birden çok işlem tarafından kullanılacak şekilde Q# , her biri için bir tane örnekliyoruz. Bunun nedeni, nesnelerin kendisi hedef makineler olarak kullanıldığında değiştirilmektedir ve sonuçları daha sonra sınıf yöntemiyle elde edilebilir `.ToTSV()` .

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

## <a name="no-locq-jupyter-notebooks"></a>Q# Jupyıter Not defterleri
Q# Jupyter Not defterleri, Q# Q# tüm yönergeler, notlar ve diğer içeriklerden---tek bir not defterinde callables tanımlamanızı, derlemenize ve çalıştırmanıza olanak tanıyan ı çekirdeğini kullanır.
Bu, dosyaların içeriğini içeri ve dışarı aktarmak mümkün olsa `*.qs` Q# da, yürütme modelinde gerekli değildir anlamına gelir.

Burada, yukarıda tanımlanan işlemleri nasıl çalıştıracağınızı ayrıntılarız Q# , ancak Q# [giriş Q# ve jupi](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)Not defterleri Ile jupi not defterlerini kullanma hakkında daha geniş bir giriş sunulmaktadır.

### <a name="defining-operations"></a>İşlemleri tanımlama

Bir Q# Jupyter Notebook, Q# kodu bir dosyanın ad alanının içinden yaptığımız gibi girersiniz Q# .

Bu nedenle, ilgili ad alanları için deyimlerle [ Q# Standart kitaplıklardan](xref:microsoft.quantum.qsharplibintro) callables 'e erişimi etkinleştirebiliriz `open` .
Bu tür bir deyime sahip bir hücreyi çalıştırırken, bu ad alanlarından alınan tanımlar çalışma alanı boyunca kullanılabilir.

> [!NOTE]
> [Microsoft. hisse. iç](xref:microsoft.quantum.intrinsic) ve [Microsoft. hisse. Canon](xref:microsoft.quantum.canon) (örn.) ile callables [`H`](xref:microsoft.quantum.intrinsic.h) [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) , Q# jupi Not defterlerindeki hücrelerde tanımlanan işlemler için otomatik olarak kullanılabilir.
> Ancak, bu, dış Q# kaynak dosyalarından ( [giriş Q# ve jupi not defterlerine](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)göre gösterilen bir işlem) getirilen kod için doğru değildir. 
> 

Benzer şekilde, tanımlama işlemleri yalnızca kodu yazmak Q# ve hücreyi çalıştırmak için gereklidir.

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="773">

Daha sonra çıktı bu işlemleri listeler, daha sonra gelecekteki hücrelerden çağrılabilir.

### <a name="target-machines"></a>Hedef makineler

Belirli hedef makinelerde işlem çalıştırma işlevselliği [I Q# Magic komutları](xref:microsoft.quantum.guide.quickref.iqsharp)aracılığıyla sağlanır.
Örneğin, `%simulate` `QuantumSimulator` öğesini kullanır ve şunları `%estimate` kullanır `ResourcesEstimator` :

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a Q# operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a>İşlevlere ve işlemlere giriş geçirme

Q#İşlemleri işlemlere geçirmek için bağımsız değişkenler `key=value` yürütme Magic komutuna çiftler olarak geçirilebilir.
Bu nedenle, `MeasureSuperpositionArray` dört qubit ile çalıştırmak için şunları çalıştırabiliriz `%simulate MeasureSuperpositionArray n=4` :

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a Q# operation with arguments" width="773">

Bu model, `%estimate` ve diğer yürütme komutlarıyla benzer şekilde kullanılabilir.

### <a name="using-no-locq-code-from-other-projects-or-packages"></a>Q#Diğer projelerden veya paketlerdeki kodu kullanma

Varsayılan olarak, bir Q# Jupyter Notebook tüm `.qs` dosyaları geçerli klasöre yükler ve Q# işlemlerini ve işlevlerini Not defterinin içinden kullanıma sunar. [ `%who` MAGIC komutu](xref:microsoft.quantum.iqsharp.magic-ref.who) , mevcut olan tüm Q# işlemleri ve işlevleri listeler.

Başka bir Q# klasörden kod yüklemek için, [ `%project` MAGIC komutu](xref:microsoft.quantum.iqsharp.magic-ref.project) bir proje için bir dosyaya başvuru eklemek için kullanılabilir `.csproj` (yani Q# , başvuru yapan bir proje `Microsoft.Quantum.Sdk` ). Bu komut `.qs` , `.csproj` (ve alt klasörleri) içeren klasörde bulunan dosyaları derler. Ayrıca, `PackageReference` ya da Q# Bu dosyanın üzerinden başvurulan projeler aracılığıyla başvurulan paketleri yinelemeli olarak yükler `ProjectReference` `.csproj` . 

Örnek olarak, aşağıdaki hücreler, Q# Proje yolunun geçerli klasöre göre başvurduğu bir dış projeden bir işlemin benzetimini yapar:

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a Q# operation from an external project" width="773">

Kod içeren harici paketleri yüklemek için Q# [ `%package` Magic komutunu](xref:microsoft.quantum.iqsharp.magic-ref.package)kullanın.
Bir paketin yüklenmesi, özel bir Magic komutu da kullanılabilir hale getirir veya paketin parçası olan tüm derlemelerde bulunan kodlayıcıları görüntüler.

Q#Not defteri başlatma zamanında dış paketleri veya projeleri yüklemek için Not defteri klasörünün başvuran bir dosya içerdiğinden emin olun `.csproj` `Microsoft.Quantum.Sdk` . Bu durumda, `.csproj` özelliğini öğesine ekleyin `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` `<PropertyGroup>` . Bu, içinde bulunan Q# `ProjectReference` ve `PackageReference` `.csproj` Not defteri yükleme sırasında bulunan ' de bulunan her türlü öğeyi yinelemeli olarak yüklemeyi ister.

Örneğin, `.csproj` Q# paketi otomatik olarak yükleyemem neden olan basit bir dosya aşağıda verilmiştir `Microsoft.Quantum.Chemistry` :

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> Şu anda bu özel `<IQSharpLoadAutomatically>` özellik Q# Jupyter Notebook konakları için gereklidir, ancak gelecekte bu durum, `.csproj` Not defteri dosyasıyla aynı klasörde bulunan bir dosya için varsayılan davranış haline gelebilir.

> [!NOTE]
> `<QsharpCompile>`' Deki ayarı şu anda `.csproj` Jupyter Notebook konakları tarafından yok sayılır Q# ve `.qs` `.csproj` (alt klasörler dahil) klasöründeki tüm dosyalar yüklenir ve derlenir. `.csproj`Gelecekte ayarlar için destek sunulacaktır (daha fazla ayrıntı için bkz. [ıqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) ).
