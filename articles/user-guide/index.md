---
title: Q# Kullanıcı Kılavuzu
description: Kullanıcı Kılavuzunun amacına ve içeriğine yönelik genel bakış
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: f535aaedbe6ce181375d48f7023409ad8212c702
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430620"
---
# <a name="the-q-user-guide"></a>Q# Kullanıcı Kılavuzu

Q# Kullanıcı Kılavuzu’na hoş geldiniz! 

Burada Q# diline ait temel kavramların ve kuantum programları yazmak için ihtiyaç duyduğunuz bilgilerin ayrıntılarını paylaşıyoruz.

## <a name="user-guide-contents"></a>Kullanıcı Kılavuzu İçeriği

- [Q# Hakkındaki Temel Bilgiler](xref:microsoft.quantum.guide.basics): Q# programlama dilinin amacı ve işlevlerine yönelik genel bir bakış. 

### <a name="q-language"></a>Q# Dili

- [Q# Dilindeki Türler](xref:microsoft.quantum.guide.types): Q# tür modelini yerleştirir ve türleri belirtip bunlarla çalışmaya yönelik söz dizimini açıklar.

- [Tür İfadeleri](xref:microsoft.quantum.guide.expressions): Q# dilindeki her türe ait değeri belirtme, birleştirme ve bu değere başvurup değer üzerinde çalışma ayrıntıları. 

### <a name="using-q"></a>Q# kullanma

- [Q# Dosya Yapısı](xref:microsoft.quantum.guide.filestructure): `*.qs` Q# dosyasının yapısını ve söz dizimini açıklar.

- [İşlemler ve İşlevler](xref:microsoft.quantum.guide.operationsfunctions): Q# dilinin çağrılabilir iki türü hakkında ayrıntılar sağlar: *işlemler*, kubit kayıt defterleri üzerindeki eylemleri içerir ve *işlevler*, yalnızca klasik bilgilerle çalışır. 
    Burada, kuantum işlemlerinin eklenik ve denetlenmiş sürümleri dahil olmak üzere bunları nasıl tanımlayıp çağıracağınızı göreceksiniz.

- [Değişkenler](xref:microsoft.quantum.guide.variables): Q# programlarındaki değişkenlerin rolünü ve bunların nasıl etkili bir şekilde kullanılacağını açıklar. 
    Örneğin, bağlama kapsamlarının yanı sıra, sabit/değişebilen değişkenler arasındaki farklar ve bunları atayıp atamalarını kaldırma hakkında bilgiler bulabilirsiniz.

- [Kubitlerle çalışma](xref:microsoft.quantum.guide.qubits): Tek başına kubitlere ve kubit sistemlerine yönelik olarak kullanılan Q# özelliklerini açıklar. 
    Özellikle, bunların ayrılmasını, bunlara yönelik işlemler gerçekleştirmeyi ve son olarak ölçülerini kapsar. 

- [Denetim Akışı](xref:microsoft.quantum.guide.controlflow): Çok sayıda standart tekniğin (koşullu yürütme, for döngüleri, while döngüleri vb.) yanı sıra kuantuma özgü “Başarılı Olana Kadar Yinele” desenini de içeren, Q# dilindeki programlama denetim akışı desenlerinin ayrıntılarını içerir.

- [Test ve hata ayıklama](xref:microsoft.quantum.guide.testingdebugging): Kodunuzun doğru şekilde çalıştığından emin olmaya yönelik bazı teknikleri açıklar. 
    Kuantum bilgilerinin genel opaklığı nedeniyle, bir kuantum programında hata ayıklamak için özel teknikler gerekebilir. 
    Neyse ki, Q# kuantuma özgü tekniklerin yanı sıra klasik hata ayıklama tekniklerinin birçoğunu destekler. Bunlar Q# içinde birim testi oluşturmayı/çalıştırmayı, kodunuzda değerlere ve olasılıklara *onay deyimi* eklemeyi ve hedef makine durumunun çıkışını oluşturan `Dump` işlevlerini içerir. 
    Sonuncusu, bazı kuantum sınırlamalarını (ör. kopyalamama teoremi) atlayarak işlemlerin belirli bölümlerinde hata ayıklamak için tam durum simülatörümüzle birlikte kullanılabilir.

### <a name="quantum-simulators-and-resource-estimators"></a>Kuantum Simülatörleri ve Kaynak Tahmin Araçları

- [Kuantum simülatörleri ve konak uygulamaları](xref:microsoft.quantum.machines): Kullanılabilen farklı simülatörlerin yanı sıra, konak program ve hedef makineler arasındaki genel yürütme modeline yönelik bir genel bakış.

- [Tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator): Tam kuantum durumunu simüle eden hedef makine. Daha küçük ölçekli programları (birkaç düzine kubitten küçük) tamamen yürütme veya bunlarda hata ayıklamada kullanılır

- [Kaynak tahmin aracı](xref:microsoft.quantum.machines.resources-estimator): Bir kuantum bilgisayarda Q# işleminin belirli bir örneğini çalıştırmak için gereken kaynaklara yönelik tahmin yapar.

- [İzleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro): kuantum bilgisayarın durumunu gerçekten taklit etmeden bir kuantum programı yürütür ve böylece binlerce kubit kullanan kuantum programlarını da yürütülebilir. Bir kuantum programındaki klasik kodda hata ayıklamak ve gerekli kaynakları tahmin etmek için yararlıdır.

- [Toffoli simülatörü](xref:microsoft.quantum.machines.toffoli-simulator): Milyonlarca kubitle kullanılabilen özel amaçlı bir kuantum simülatörü. Yalnızca kısıtlanmış kuantum işlemleri kümesi içeren programlar içindir (örneğin X, CNOT ve çok denetimli X).

### <a name="quick-reference-pages"></a>Hızlı Başvuru Sayfaları

- [IQ# Magic Komutları](xref:microsoft.quantum.guide.quickref.iqsharp): Q# Jupyter Notebook’lardaki IQ# magic komutlarına yönelik hızlı başvuru sayfası.
