---
title: Kuantum simülatörleri ve konak uygulamaları | Microsoft Docs
description: Genellikle C# veya Q# olmak üzere klasik bir bilgi işlem .NET dili ile kuantum simülatörleri çalıştırmayı açıklar.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 14aed75ed0ed192f88699b1c7dbacfae23f74642
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442224"
---
# <a name="quantum-simulators-and-host-applications"></a>Kuantum simülatörleri ve konak uygulamaları

## <a name="what-youll-learn"></a>Öğrenecekleriniz

> [!div class="checklist"]
> * Kuantum algoritmalar nasıl yürütülür?
> * Bu sürüme dahil olan kuantum simülatörler
> * Kuantum algoritmanız için bir C# sürücüsü yazma

## <a name="the-quantum-development-kit-execution-model"></a>Kuantum Geliştirme Seti Yürütme Modeli

[Kuantum program yazma](xref:microsoft.quantum.write-program) bölümünde bir `QuantumSimulator` nesnesini algoritma sınıfının `Run` yöntemine geçirerek kuantum algoritmamızı yürüttük.
`QuantumSimulator` sınıfı, `Teleport` çalıştırmak ve test etmek için mükemmel olan kuantum durum vektörünü tamamen taklit ederek kuantum algoritmasını yürütür.
Kuantum durum vektörleri hakkında daha fazla bilgi için bkz. [Kavramlar kılavuzu](xref:microsoft.quantum.concepts.intro).

Diğer hedef makineler bir kuantum algoritması çalıştırmak için kullanılabilir.
Makine, algoritma için kuantum temel elemanlarının uygulamasını sağlamaktan sorumludur.
Buna H, CNOT ve Measure gibi temel eleman işlemlerinin yanı sıra kuantum bit yönetimi ve izlemesi dahildir.
Farklı kuantum makine sınıfları, aynı kuantum algoritması için farklı yürütme modellerini temsil eder.

Her kuantum makine türü, bu temel elemanların farklı uygulamalarını sağlayabilir.
Örneğin, geliştirme setine dahil olan kuantum bilgisayar iz simülatörü hiçbir simülasyon yapmaz.
Bunun yerine algoritmaya ait geçit, kuantum bit ve diğer kaynak kullanımını izler.

### <a name="quantum-machines"></a>Kuantum Makineler

Gelecekte diğer simülasyon türlerini destekleyen ve topolojik kuantum bilgisayarlar üzerinde yürütmeyi destekleyen başka kuantum makine sınıfları tanımlayacağız.
Temel alınan makine uygulamasını değiştirirken algoritmanın sabit kalmasına izin vermek, simülasyondaki bir algoritmayı test etme ve hata ayıklama işlemlerini kolaylaştırır ve sonra algoritmanın değişmediğinden emin olarak gerçek donanım üzerinde rahatça çalıştırılır.

### <a name="whats-included-in-this-release"></a>Bu Yayına Dahil Olan Özellikler

Kuantum geliştirici setinin bu yayını birkaç kuantum makine sınıfı içerir.
Bu sınıfların tümü `Microsoft.Quantum.Simulation.Simulators` ad alanında tanımlanmıştır.

* Bir [tam durum vektör simülatörü](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` sınıfı.
* Bir [basit kaynak tahmin aracı](xref:microsoft.quantum.machines.resources-estimator), `ResourcesEstimator` sınıfı. Bir kuantum algoritmasını çalıştırmak için gereken kaynakların üst düzey analizini yapmaya olanak tanır.
* [İzleme tabanlı kaynak tahmin aracı](xref:microsoft.quantum.machines.qc-trace-simulator.intro), `QCTraceSimulator` sınıfı. Algoritmanın tüm çağrı grafı için kaynak tüketiminin gelişmiş analizini yapmaya olanak tanır.
* Bir [Toffoli simülatörü](xref:microsoft.quantum.machines.toffoli-simulator), `ToffoliSimulator` sınıfı.

## <a name="writing-a-host-application"></a>Konak uygulama yazma

[Kuantum program yazma](xref:microsoft.quantum.write-program) bölümünde teleport algoritmamız için basit bir C# sürücüsü yazmıştık. Bir C# sürücüsünün başlıca 4 amacı vardır:

* Hedef makineyi oluşturma
* Kuantum algoritması için gereken tüm bağımsız değişkenleri hesaplama
* Simülatörü kullanarak kuantum algoritması çalıştırma
* İşlemin sonucunu işleme

Burada her adımı daha ayrıntılı olarak ele alacağız.

### <a name="constructing-the-target-machine"></a>Hedef Makineyi Oluşturma

Kuantum makineler normal .NET sınıfı örnekleridir, bu nedenle herhangi bir .NET sınıfı gibi oluşturucularını çağırarak oluşturulurlar.
`QuantumSimulator` dahil bazı simülatörler .NET <xref:System.IDisposable?displayProperty=nameWithType> arabirimini uygular ve bu yüzden bir C# `using` deyimine sarmalanmalıdır.

### <a name="computing-arguments-for-the-algorithm"></a>Algoritma Bağımsız Değişkenlerini Hesaplama

`Teleport` örneğimizde, kuantum algoritmamıza geçirilecek bazı görece yapay bağımsız değişkenleri hesaplandık.
Bununla birlikte, genellikle kuantum algoritması önemli veriler gerektirir ve bu verileri klasik sürücüden sağlamak en kolay yoldur.

Örneğin, kimyasal simülasyonlar yaparken kuantum algoritması büyük bir moleküler orbital etkileşim tam sayıları tablosu gerektirir.
Bunlar genellikle algoritma çalıştırılırken sağlanan bir dosyadan okunurlar.
Q# dilinin dosya sistemine erişmeye yönelik bir mekanizması bulunmadığı için, bu tür verileri toplamanın en iyi yolu klasik sürücüdür ve bu veriler kuantum algoritmasının `Run` yöntemine geçirilir.

Klasik sürücünün anahtar rol oynadığı başka bir durum ise değişimli yöntemlerde yaşanır.
Bu algoritma sınıfında bazı klasik parametreler temel alınarak bir kuantum durumu hazırlanır ve bu durum, bazı ilgili değerleri hesaplamak için kullanılır.
Parametreler bazı tırmanma veya makine öğrenmesi algoritması türleri temel alınarak ayarlanır ve kuantum algoritması tekrar çalışır.
Bu tür algoritmalar için tırmanma algoritmasını uygulamanın en iyi yolu, klasik sürücü tarafından çağrılan tamamen klasik bir işlev olarak uygulamaktır. Tırmanma sonuçları daha sonra kuantum algoritmasının sonraki yürütme işlemine geçirilir.

### <a name="running-the-quantum-algorithm"></a>Kuantum Algoritmasını Çalıştırma

Bu bölüm genellikle çok basittir.
Her Q# işlemi statik bir `Run` yöntemi sağlayan bir sınıfta derlenir.
Bu yöntemin bağımsız değişkenleri, işlemin düzleştirilmiş bağımsız değişken demeti tarafından verilir ve ek olarak, yürütülecek simülatörü oluşturan bir birinci bağımsız değişken daha bulunur. `(a: String, (b: Double, c: Double))` türünde adlandırılmış demeti bekleyen bir işlemin düzleştirilmiş karşılığı `(String a, Double b, Double c)` türündedir.


Bağımsız değişkenleri bir `Run` yöntemine geçirirken uygulanacak bazı incelikler vardır:

* Diziler bir `Microsoft.Quantum.Simulation.Core.QArray<T>` nesnesine sarmalanmış olmalıdır.
    `QArray` sınıfı, uygun nesnelerin sıralanmış herhangi bir koleksiyonunu (`IEnumerable<T>`) alabilen bir oluşturucuya sahiptir.
* Q# dilinde `()` olan boş demet, C# dilinde `QVoid.Instance` ile temsil edilir.
* Boş olmayan demetler .NET `ValueTuple` örnekleri olarak temsil edilir.
* Kullanıcı tanımlı Q# türleri, temel tür olarak geçirilir.
* Bir işlemi veya işlevi `Run` yöntemine geçirmek için, simülatörün `Get<>` yöntemini kullanarak işlemin veya işlevin sınıfının bir örneğini elde etmeniz gerekir.

### <a name="processing-the-results"></a>Sonuçları İşleme

Kuantum algoritmasının sonuçları `Run` yönteminden döndürülür.
`Run` yöntemi zaman uyumsuz olarak yürütülür, bu nedenle bir <xref:System.Threading.Tasks.Task`1> örneği döndürür.
Gerçek işlemin sonuçlarını almanın birden çok yolu vardır. En basit yol, `Task` yönteminin [`Result` özelliğini](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result) kullanmaktır:

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
Ancak [`Wait` yöntemini](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) veya C# [`await` anahtar sözcüğünü](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) kullanmak gibi diğer teknikler de işe yarar.

Bağımsız değişkenlerde olduğu gibi, Q# demetleri `ValueTuple` örnekleri ve Q# dizileri `QArray` örnekleri olarak temsil edilir.
Kullanıcı tanımlı türler, temel türleri olarak döndürülür.
`()` boş demeti, `QVoid` sınıfının bir örneği olarak döndürülür.

Birçok kuantum algoritması yararlı yanıtlar elde etmek için önemli miktarda son işlem gerektirir.
Örneğin, Shor algoritmasının kuantum kısmı, bir sayının faktörlerini bulan hesaplamanın yalnızca başlangıcıdır.

Çoğu durumda, bu son işlemi klasik sürücüde yapmak daha basit ve kolaydır.
Yalnızca klasik sürücü sonuçları kullanıcıya bildirebilir veya diske yazabilir.
Klasik sürücü, analitik kitaplıklara ve Q# içinde gösterilmeyen diğer matematiksel işlevlere erişebilir.


## <a name="failures"></a>Hatalar

Bir işlemin yürütülmesi sırasında Q# `fail` deyimine ulaşıldığında bir `ExecutionFailException` oluşturulur.

`Run` yönteminde `System.Task` kullanılması nedeniyle, `fail` deyiminin sonucu olarak oluşturulan özel durum bir `System.AggregateException` içine sarmalanmalıdır.
Hatanın gerçek nedenini bulmak için `AggregateException` 
`InnerExceptions`içinde tekrarlamanız gerekir, örneğin:

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a>Diğer Klasik Diller

Sağladığımız örnekler C#, F# ve Python dillerinde olsa da Kuantum Geliştirme Seti diğer dillerde klasik ana bilgisayar programları yazmayı da destekler.
Örneğin, Visual Basic’te bir ana bilgisayar programı yazmak istiyorsanız [sorunsuzca çalışmalıdır](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).
