---
title: IQ# Magic Komutları
description: 'Q # Jupyıter Not defterleri ile IQ # Magic komutları için hızlı başvuru sayfası'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 2fb542df8723fa437c82b4a1dfada77e22c1d6e4
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870557"
---
# <a name="iq-magic-commands"></a>IQ# Magic Komutları

### <a name="general"></a>Genel

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Yapılandırma seçeneklerinin ayarlanmasına veya sorgulanmasına izin verir.
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): ResourcesEstimator hedef makinesinde belirli bir işlevi veya işlemi çalıştırır.
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Şu anda kullanılabilir olan tüm sihirli komutlarının listesini döndürür.
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Bir NuGet paketini yükleme özelliği sağlar.
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): Bu çekirdek için geçerli performans ölçümlerini raporlar.
- [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Belirtilen işlevi veya işlemi, miktar Tumsimülatör hedef makinesinde çalıştırır.
- [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Toffkaysimülatör hedef makinesinde belirli bir işlevi veya işlemi çalıştırır.
- [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Geçerli oturumda kullanılabilir olan Q # işlemlerini listeler.
- [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Geçerli çalışma alanıyla ilgili eylemleri sağlar.

### <a name="azure-quantum-integration"></a>Azure hisse tümleştirme

- [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Bir Azure hisse çalışma alanına bağlanır veya geçerli bağlantı durumunu görüntüler.
- [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Bir işi Azure hisse çalışma alanında yürütür.
- [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Geçerli Azure hisse çalışma alanındaki işlerin listesini görüntüler.
- [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Geçerli Azure hisse çalışma alanındaki bir işin sonuçlarını görüntüler.
- [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Geçerli Azure hisse çalışma alanındaki bir işin durumunu görüntüler.
- [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Bir Azure hisse çalışma alanına iş gönderir.
- [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Bir Azure hisse çalışma alanında Q # işi gönderimi için etkin yürütme hedefini ayarlar veya görüntüler.

### <a name="chemistry-from-microsoftquantumchemistry-package"></a>Chemistry (Microsoft. hisse. Chemistry paketinden)

- [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): Belirli bir. YAML dosyasından Broombridge elektronik yapısı sorun gösterimini yükler ve döndürür.
- [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Bir fermıon Hamiltonian 'yi, Q # tarafından tüketilen bir biçime kodluyor.
- [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Bir fermıon Hamiltonian için terimler ekler.
- [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): Elektronik bir yapı sorunu için fermıon Hamiltonian 'i yükler. Sorun bir dosyadan yüklenir veya bağımsız değişken olarak geçirilir.
- [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Broombridge elektronik yapısı sorununu yükler ve seçili giriş durumunu döndürür.

### <a name="katas-from-microsoftquantumkatas-package"></a>Katas (Microsoft. hisse. katas paketinden)

- [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): Tek bir test yürütür ve testin başarıyla başarılı olup olmadığını bildirir.
- [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): Tek bir küta 'nın test için başvuru uygulamasını denetler.
    Özellikle, tek bir görev için başvuru uygulamasını hücreye koyar ve testin başarıyla başarılı olup olmadığını bildirir.
