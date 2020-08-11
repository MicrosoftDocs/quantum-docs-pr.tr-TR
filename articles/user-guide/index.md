---
title: Q# Kullanıcı Kılavuzu
description: Kullanıcı Kılavuzunun amacına ve içeriğine yönelik genel bakış
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4fae2949bdcab0c3735b40ef029d70bf7ea3fb9f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869639"
---
# <a name="the-no-locq-user-guide"></a>Q# Kullanıcı Kılavuzu

Q# Kullanıcı Kılavuzu’na hoş geldiniz! 

Bu kılavuzun farklı konularında, Q# diline ait temel kavramların ve kuantum programları yazmak için ihtiyaç duyduğunuz bilgilerin ayrıntılarını paylaşıyoruz.

## <a name="user-guide-contents"></a>Kullanıcı Kılavuzu İçeriği

- [Q# Temel Bilgileri](xref:microsoft.quantum.guide.basics): Q# programlama dilinin amacı ve işlevselliğine yönelik tanıtıcı bir genel bakış. 

- [Q# programını çalıştırma yolları](xref:microsoft.quantum.guide.host-programs): Q# programının nasıl yürütüleceğini açıklar ve şunlar gibi, programı çağırabileceğiniz çeşitli yöntemlere genel bir bakış sunar: komut satırından, Q# Jupyter Not Defterleri içinde veya Python ya da bir .NET dilinde yazılmış klasik konak programından.

### <a name="no-locq-language"></a>Q# Dili

- [Q# dilindeki türler](xref:microsoft.quantum.guide.types): Q# tür modeline açıklık getirir ve türleri belirtip bunlarla çalışmaya yönelik söz dizimini açıklar.

- [Tür İfadeleri](xref:microsoft.quantum.guide.expressions): Q# dilindeki her türdeki değerleri belirtme, birleştirme ve bu değerlere başvurup üzerlerinde çalışmayı ayrıntılarıyla açıklar. 

### <a name="using-no-locq"></a>Q# kullanma

- [Q# Dosya Yapısı](xref:microsoft.quantum.guide.filestructure): `*.qs` Q# dosyasının yapısını ve söz dizimini açıklar.

- [İşlemler ve İşlevler](xref:microsoft.quantum.guide.operationsfunctions): Q# dilinin çağrılabilir iki türü hakkında ayrıntılar sağlar: *işlemler*, kubit yazmaçları üzerindeki eylemleri içerir ve *işlevler*, yalnızca klasik bilgilerle çalışır. 
    Burada, kuantum işlemlerinin eklenik ve denetlenmiş sürümleri dahil olmak üzere bunları nasıl tanımlayıp çağıracağınızı göreceksiniz.

- [Değişkenler](xref:microsoft.quantum.guide.variables): Q# programlarındaki değişkenlerin rolünü ve bunların nasıl etkili bir şekilde kullanılacağını açıklar. 
    Örneğin, bağlama kapsamlarının yanı sıra, sabit ve değişebilen değişkenler arasındaki fark ve bunları atayıp atamalarını kaldırma hakkında bilgiler bulabilirsiniz.

- [Kubitlerle çalışma](xref:microsoft.quantum.guide.qubits): Tek tek kubitleri ve kubit sistemlerini adreslemek için kullanılan Q# özelliklerini, özellikle bunları ayırmayı, bunlar üzerinde işlem gerçekleştirmeyi ve bunları ölçmeyi açıklar. 

- [Denetim Akışı](xref:microsoft.quantum.guide.controlflow): Çok sayıda standart tekniğin (koşullu yürütme, for döngüleri, while döngüleri gibi) yanı sıra kuantuma özgü “Başarılı Olana Kadar Yinele” desenini de içeren, Q# dilindeki kullanılabilir programlama denetim akışı desenlerini ayrıntılarıyla açıklar.

- [Test etme ve hata ayıklama](xref:microsoft.quantum.guide.testingdebugging): Kodunuzun istendiği şekilde çalıştığından emin olmaya yönelik bazı teknikleri ayrıntılarıyla açıklar. 
    Kuantum bilgilerinin genel opaklığı nedeniyle, bir kuantum programında hata ayıklamak için özel teknikler gerekebilir. 
    Neyse ki, Q# kuantuma özgü tekniklerin yanı sıra programcıların tanıdığı klasik hata ayıklama tekniklerinin birçoğunu destekler. Bunlar Q# dilinde birim testi oluşturmayı ve çalıştırmayı, kodunuzda değerlere ve olasılıklara *onay* eklemeyi ve hedef makine durumunun çıkışını oluşturan `Dump` işlevlerini içerir. 
    Sonuncusu, bazı kuantum sınırlamalarını (örneğin, [kopyalamama teoremi](xref:microsoft.quantum.concepts.pauli)) atlayarak hesaplamaların belirli bölümlerinde hata ayıklamak için tam durumlu simülatörümüzle birlikte kullanılabilir.

### <a name="quantum-simulators-and-resource-estimators"></a>Kuantum Simülatörleri ve Kaynak Tahmin Araçları

- [Kuantum simülatörleri ve konak uygulamaları](xref:microsoft.quantum.machines): Kullanılabilir farklı simülatörlerin yanı sıra, konak programlar ve hedef makineler arasındaki genel yürütme modeline yönelik bir genel bakış.

- [Tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator): Tam kuantum durumunun simülasyonunu yapan hedef makine. Daha küçük ölçekli programları (birkaç düzine kubitten küçük) tamamen yürütmek veya bunlarda hata ayıklamak için faydalıdır

- [Kaynak tahmin aracı](xref:microsoft.quantum.machines.resources-estimator): Bir kuantum bilgisayarda Q# işleminin belirli bir örneğini çalıştırmak için gereken kaynaklara yönelik tahmin yapar.

- [İzleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Kuantum bilgisayar durumunun simülasyonunu yapmadan bir kuantum programı yürütür ve böylece binlerce kubit kullanan kuantum programlarını da yürütülebilir. Bir kuantum programındaki klasik kodda hata ayıklamak ve gerekli kaynakları tahmin etmek için yararlıdır.

- [Toffoli simülatörü](xref:microsoft.quantum.machines.toffoli-simulator): Milyonlarca kubitle kullanılabilen özel amaçlı bir kuantum simülatörü. Yalnızca kısıtlanmış kuantum işlemleri kümesi içeren programlar içindir (örneğin X, CNOT ve çok denetimli X).

### <a name="quick-reference-pages"></a>Hızlı Başvuru Sayfaları

- [IQ# Magic Komutları](xref:microsoft.quantum.guide.quickref.iqsharp): Q# Jupyter Not Defterlerindeki IQ# magic komutlarına yönelik hızlı başvuru sayfası.
