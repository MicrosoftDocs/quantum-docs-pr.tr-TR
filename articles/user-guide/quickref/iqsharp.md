---
title: IQ# Magic Komutları
description: 'Q # Jupyıter Not defterleri ile IQ # Magic komutları için hızlı başvuru sayfası'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431028"
---
# <a name="iq-magic-commands"></a>IQ# Magic Komutları

### <a name="general"></a>Genel

- `%config`: Yapılandırma tercihlerini ayarlar veya alır.
- `%estimate`: Belirtilen işlevi veya işlemi, miktar Tumsimülatör hedef makinesinde çalıştırır.
- `%lsmagic`: Şu anda kullanılabilir olan tüm sihirli komutlarının listesini döndürür.
- `%package`: Bir NuGet paketini yükleme özelliği sağlar.
- `%performance`: Bu çekirdek için geçerli performans ölçümlerini raporlar.
- `%simulate`: Belirtilen işlevi veya işlemi, miktar Tumsimülatör hedef makinesinde çalıştırır.
- `%toffoli`: Toffzeytin simülatör hedef makinesi üzerinde belirli bir işlevi veya işlemi çalıştırır.
- `%who`: Geçerli çalışma alanıyla ilgili eylemleri sağlar.
- `%workspace`: Etkileşimli veya geçerli çalışma alanından yüklenen geçerli oturumda tanımlanan tüm işlem ve işlevlerin listesini döndürür.

### <a name="chemistry"></a>Kimya

- `%chemistry.broombridge`: Belirli bir. YAML dosyasından Broombridge elektronik yapısı sorun gösterimini yükler ve döndürür.
- `%chemistry.encode`: Bir fermıon Hamiltonian 'yi, Q # tarafından tüketilen bir biçime kodluyor.
- `%chemistry.fh.add_terms`: Bir fermıon Hamiltonian için terimler ekler.
- `%chemistry.fh.load`: Elektronik bir yapı sorunu için fermıon Hamiltonian 'i yükler. Sorun bir dosyadan yüklenir veya bağımsız değişken olarak geçirilir.
- `%chemistry.inputstate.load`: Broombridge elektronik yapısı sorununu yükler ve seçili giriş durumunu döndürür.

### <a name="from-microsoftquantumkatas-package"></a>Microsoft. hisse. katas paketinden

- `%kata`: Tek bir test yürütür ve testin başarıyla başarılı olup olmadığını bildirir.
- `%check_kata`: Tek bir küta 'nın test için başvuru uygulamasını denetler.
    Özellikle, tek bir görev için başvuru uygulamasını hücreye koyar ve testin başarıyla başarılı olup olmadığını bildirir.
