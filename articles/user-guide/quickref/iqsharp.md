---
title: I Q# Magic komutları
description: Q#Jupyıter Not defterleri ile I Magic komutları için hızlı başvuru sayfası Q#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1d2d092588e1a5c69d12e5d50377e3e26412c094
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863689"
---
# <a name="ino-locq-magic-commands"></a>I Q# Magic komutları

### <a name="general"></a>Genel

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Yapılandırma seçeneklerinin ayarlanmasına veya sorgulanmasına izin verir.
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): ResourcesEstimator hedef makinesinde belirli bir işlevi veya işlemi çalıştırır.
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Şu anda kullanılabilir olan tüm sihirli komutlarının listesini döndürür.
- [`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen): Şu anda açık olan ad alanlarını ve bunların diğer adlarını listeler.
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Bir NuGet paketini yükleme özelliği sağlar.
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): Bu çekirdek için geçerli performans ölçümlerini raporlar.
- [`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project): Proje başvurularını görüntüleme veya ekleme özelliği sağlar Q# . 
- [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Belirtilen işlevi veya işlemi, miktar Tumsimülatör hedef makinesinde çalıştırır.
- [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Toffkaysimülatör hedef makinesinde belirli bir işlevi veya işlemi çalıştırır.
- [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Q# Geçerli oturumdaki kullanılabilir işlemleri listeler.
- [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Geçerli çalışma alanıyla ilgili eylemleri sağlar.

### <a name="azure-quantum-integration"></a>Azure hisse tümleştirme

- [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Bir Azure hisse çalışma alanına bağlanır veya geçerli bağlantı durumunu görüntüler.
- [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Bir işi Azure hisse çalışma alanında yürütür.
- [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Geçerli Azure hisse çalışma alanındaki işlerin listesini görüntüler.
- [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Geçerli Azure hisse çalışma alanındaki bir işin sonuçlarını görüntüler.
- [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Geçerli Azure hisse çalışma alanındaki bir işin durumunu görüntüler.
- [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Bir Azure hisse çalışma alanına iş gönderir.
- [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Q# Bir Azure hisse çalışma alanında iş gönderimi için etkin yürütme hedefini ayarlar veya görüntüler.

### <a name="chemistry-from-microsoftquantumchemistry-package"></a>Chemistry (Microsoft. hisse. Chemistry paketinden)

- [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): Belirli bir. YAML dosyasından Broombridge elektronik yapısı sorun gösterimini yükler ve döndürür.
- [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Bir fermıon Hamiltonian 'yi, tarafından tüketilen bir biçime kodluyor Q# .
- [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Bir fermıon Hamiltonian için terimler ekler.
- [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): Elektronik bir yapı sorunu için fermıon Hamiltonian 'i yükler. Sorun bir dosyadan yüklenir veya bağımsız değişken olarak geçirilir.
- [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Broombridge elektronik yapısı sorununu yükler ve seçili giriş durumunu döndürür.

### <a name="katas-from-microsoftquantumkatas-package"></a>Katas (Microsoft. hisse. katas paketinden)

- [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): Tek bir test yürütür ve testin başarıyla başarılı olup olmadığını bildirir.
- [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): Tek bir küta 'nın test için başvuru uygulamasını denetler.
    Özellikle, tek bir görev için başvuru uygulamasını hücreye koyar ve testin başarıyla başarılı olup olmadığını bildirir.
