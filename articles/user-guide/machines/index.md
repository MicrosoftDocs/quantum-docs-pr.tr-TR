---
title: Kuantum simülatörleri ve Q# programları
description: Q# programları için hedef makineler olarak kullanılabilen kuantum simülatörlerini açıklar.
author: QuantumWriter
ms.author: v-benbra
ms.date: 6/17/2020
ms.topic: conceptual
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: 408c636d5383cf594e7ebec6ab2edd66e20ffb82
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858778"
---
# <a name="quantum-simulators"></a>Kuantum simülatörleri

Kuantum simülatörleri, klasik bilgisayarlarda çalışıp bir Q# programı için *hedef makine* işlevi görerek, kubitlerin farklı işlemlere nasıl tepki vereceğini tahmin eden bir ortamda kuantum programları çalıştırıp test etmeyi mümkün hale getiren yazılım programlarıdır. Bu makalede, Quantum geliştirme seti’ne (QDK) dahil edilen kuantum simülatörleri ve bir Q# programını kuantum simülatörlerine geçirmenin farklı yolları (örneğin komut satırı aracılığıyla veya klasik bir dilde yazılmış sürücü kodunun kullanılması gibi) açıklanmaktadır.  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a>Quantum geliştirme seti (QDK) kuantum simülatörleri

Kuantum simülatörü, algoritma için kuantum temel elemanlarının uygulanmasını sağlamaktan sorumludur. Buna `H`, `CNOT` ve `Measure` gibi temel eleman işlemlerinin yanı sıra kubit yönetimi ve izlemesi de dahildir. QDK, aynı kuantum algoritması için farklı simülasyon yöntemlerini temsil eden farklı kuantum simülatörü sınıflarını içerir. 


Her kuantum simülatörü türü, bu temel elemanların farklı uygulamalarını sağlayabilir. Örneğin, [tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator), [kuantum durum vektörünün](xref:microsoft.quantum.glossary#quantum-state) tam simülasyonunu yaparak kuantum algoritmasını çalıştırırken, [kuantum bilgisayar izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) gerçek kuantum durumunu değerlendirmez. Bunun yerine algoritmaya ait geçit, kuantum bit ve diğer kaynak kullanımını izler.

### <a name="quantum-machine-classes"></a>Kuantum makine sınıfları

Gelecekte QDK, diğer simülasyon türlerini ve kuantum donanım üzerinde çalıştırmayı destekleyen başka kuantum makine sınıfları tanımlayacak. Temel alınan makine uygulamasını değiştirirken algoritmanın sabit kalmasına izin vermek, simülasyondaki bir algoritmayı test etme ve hata ayıklama işlemlerini kolaylaştırır ve sonra algoritmanın değişmediğinden emin olarak gerçek donanım üzerinde rahatça çalıştırılır.

QDK, hepsi `Microsoft.Quantum.Simulation.Simulators` ad alanında tanımlanan çeşitli kuantum makine sınıfları içerir.

|Simülatör |Sınıf|Açıklama|
|-----|------|---|
|[Tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | Kuantum algoritmalarını çalıştırıp bunların hatalarını ayıklar ve yaklaşık 30 kubitle sınırlıdır. |
|[Basit kaynak tahmin aracı](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | Bir kuantum algoritmasını çalıştırmak için gereken kaynakların üst düzey analizini gerçekleştirir ve binlerce kubiti destekler.|
|[İzleme tabanlı kaynak tahmin aracı](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |Algoritmanın tüm çağrı grafı için kaynak tüketiminin gelişmiş analizini çalıştırır ve binlerce kubiti destekler.|
|[Toffoli simülatörü](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |`X`, `CNOT` ve çok denetimli `X` kuantum işlemleriyle sınırlı olan kuantum algoritmalarının simülasyonunu yapar ve milyonlarca kubiti destekler. |

## <a name="invoking-the-quantum-simulator"></a>Kuantum simülatörünü çağırma

[Q# programı çalıştırmanın yolları](xref:microsoft.quantum.guide.host-programs) bölümünde, Q# kodunu kuantum simülatörüne geçirmenin üç yolu gösterilmektedir: 

* Komut satırını girme
* Python konak programı kullanma
* C# konak programı kullanma

Kuantum makineler normal .NET sınıfı örnekleridir, bu nedenle herhangi bir .NET sınıfı gibi oluşturucularını çağırarak oluşturulurlar. Bunu yapma şekliniz, Q# programını nasıl çalıştırdığınıza bağlıdır.

## <a name="next-steps"></a>Sonraki adımlar

* Farklı ortamlarda Q# programlarına yönelik hedef makineleri çağırma hakkındaki ayrıntılar için bkz. [Q# programı çalıştırmanın yolları](xref:microsoft.quantum.guide.host-programs).
