---
title: Q# Kullanıcı Kılavuzu
description: Kullanıcı Kılavuzunun amacına ve içeriğine yönelik genel bakış
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231766"
---
# <a name="the-no-locq-user-guide"></a>Q# Kullanıcı Kılavuzu

Q# Kullanıcı Kılavuzu’na hoş geldiniz! 

Bu kılavuzdaki farklı konularda, Q# kullanarak kuantum programları geliştirmeye yönelik bazı temel bilgiler sunulmaktadır.

Q# kuantum bilgisayar diline yönelik tam belirtim ve belgeler için [Q# dil kılavuzuna](xref:microsoft.quantum.qsharp.index) başvuracağız. 

## <a name="user-guide-contents"></a>Kullanıcı Kılavuzu İçeriği

- [Q# programları](xref:microsoft.quantum.guide.programs): Q# içinde kuantum programlarına hızlı bir giriş. 

- [Q# programı çalıştırmanın yolları](xref:microsoft.quantum.guide.host-programs): Q# programının nasıl çalıştırılacağını açıklar ve programı çağırabileceğiniz çeşitli yöntemlere ilişkin bir genel bakış sunar. Komut satırından, Q# Jupyter Not Defterleri içinde veya Python ya da bir .NET dilinde yazılmış klasik konak programından çalıştırma seçenekleri bu yöntemler arasındadır.

- [Test etme ve hata ayıklama](xref:microsoft.quantum.guide.testingdebugging): Kodunuzun istendiği şekilde çalıştığından emin olmaya yönelik bazı teknikleri ayrıntılarıyla açıklar. 
    Kuantum bilgilerinin genel opaklığı nedeniyle, bir kuantum programında hata ayıklamak için özel teknikler gerekebilir. 
    Neyse ki, Q# kuantuma özgü tekniklerin yanı sıra programcıların tanıdığı klasik hata ayıklama tekniklerinin birçoğunu destekler. Bunlar Q# dilinde birim testi oluşturmayı ve çalıştırmayı, kodunuzda değerlere ve olasılıklara *onay* eklemeyi ve hedef makine durumunun çıkışını oluşturan `Dump` işlevlerini içerir. 
    Sonuncusu, bazı kuantum sınırlamalarını (örneğin, [kopyalamama teoremi](xref:microsoft.quantum.concepts.pauli)) atlayarak hesaplamaların belirli bölümlerinde hata ayıklamak için tam durumlu simülatörümüzle birlikte kullanılabilir.

### <a name="quantum-simulators-and-resource-estimators"></a>Kuantum Simülatörleri ve Kaynak Tahmin Araçları

- [Kuantum simülatörleri ve konak uygulamaları](xref:microsoft.quantum.machines): Kullanılabilen farklı simülatörlerin yanı sıra, konak programların ve hedef makinelerin birlikte çalışarak Q# programlarını nasıl çalıştırdığına yönelik bir genel bakış.

- [Tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator): Tam kuantum durumunun simülasyonunu yapan hedef makine. Daha küçük ölçekli programları (birkaç düzine kubitten küçük) tamamen çalıştırmak veya bunlarda hata ayıklamak için faydalıdır

- [Kaynak tahmin aracı](xref:microsoft.quantum.machines.resources-estimator): Bir kuantum bilgisayarda Q# işleminin belirli bir örneğini çalıştırmak için gereken kaynaklara yönelik tahmin yapar.

- [İzleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Kuantum bilgisayar durumunun simülasyonunu yapmadan bir kuantum programı çalıştırır ve böylece binlerce kubit kullanan kuantum programlarını da çalıştırabilir. Bir kuantum programındaki klasik kodda hata ayıklamak ve gerekli kaynakları tahmin etmek için yararlıdır.

- [Toffoli simülatörü](xref:microsoft.quantum.machines.toffoli-simulator): Milyonlarca kubitle kullanılabilen özel amaçlı bir kuantum simülatörü. Yalnızca kısıtlanmış kuantum işlemleri kümesi içeren programlar içindir (örneğin X, CNOT ve çok denetimli X).

### <a name="quick-reference-pages"></a>Hızlı Başvuru Sayfaları

- [IQ# Magic Komutları](xref:microsoft.quantum.guide.quickref.iqsharp): Q# Jupyter Not Defterlerindeki IQ# magic komutlarına yönelik hızlı başvuru sayfası.
