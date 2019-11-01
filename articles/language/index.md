---
title: Q# Programlama Dili| Microsoft Docs
description: Q# Programlama Dili
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: d8759b9f043d2e13f4b0c97d54bd824c7e87d6de
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035268"
---
# <a name="the-q-programming-language"></a>Q# Programlama Dili

# <a name="introduction"></a>Giriş

Kuantum bilgisayarını GPU’lar, FPGA’lar ve diğer yardımcı işlemciler için kullanılanlara benzer şekilde bir ortak işlemci olarak işleme almak, kuantum bilişimi için doğal bir modeldir.
Birincil kontrol mantığı, klasik bir "konak" bilgisayar üzerinde klasik kod çalıştırır.
Uygun ve gerekli olduğunda, konak programı yardımcı işlemci üzerinde çalışan bir alt yordamı çağırabilir.
Alt yordam tamamlandığında, konak programı alt yordamın sonuçlarına erişim elde eder.

Q# (Q-sharp), kuantum algoritmalarını ifade etmek için kullanılan, etki alanına özel bir programlama dilidir.
Klasik bir konak program ve bilgisayarın kontrolü altında bir yardımcı kuantum işlemcisi üzerinde yürütülen alt yordamlar yazmak için kullanılır.
Kuantum işlemcileri yaygın olarak kullanılabilir hale gelene kadar Q# alt yordamları bir simülatör üzerinde yürütülür.

Q# yeni ve yapılandırılmış türler oluşturmaya yönelik iki yol (diziler ve demetler) ile birlikte küçük bir temel tür kümesi sağlar.
Döngüler ve if/then deyimleriyle program yazmaya yönelik temel bir yordamsal modeli destekler.
Q# içindeki üst düzey yapılar kullanıcı tanımlı türler, işlemler ve işlevlerdir.

Aşağıdaki bölümlerde ayrıntılı olarak şu konular açıklanmaktadır:
- [Tür Modeli](xref:microsoft.quantum.language.type-model)
- [İfadeler](xref:microsoft.quantum.language.expressions)
- [Deyimler](xref:microsoft.quantum.language.statements)
- [Dosya Yapısı](xref:microsoft.quantum.language.file-structure)

# <a name="conventions"></a>Kurallar

Tüm durumlarda genel noktalama işaretlerinin tutarlı bir şekilde kullanıldığından emin olmak için çalışıyoruz.
Bu işaretler her zaman aynı anlama geldiğinden ve aynı kavram her zaman aynı şekilde temsil edildiğinden böylece Q# dilinin daha kolay öğrenilebileceğini ve okunabileceğini umuyoruz.

Daha ayrıntılı şekilde belirtmek gerekirse:

- Noktalı virgül, `;`, bir deyimi veya tek satırlık yönergeyi sonlandırmak için kullanılır.
  Başka bir amaçla kullanılmaz.
- Virgül, `,`, bir dizinin öğelerini ayırmak için kullanılır. Demet değişmez değerleri, dizi değişmez değerleri, bağımsız değişken listeleri, demet tanımları ve tür listeleri için kullanılır. **Önceki sürümlerden farklı olarak, `;` artık bir dizi değişmez değeri ayırıcısı olarak desteklenmemektedir.**
- İki nokta üst üste, `:`, bir tür ek açıklaması oluşturmak için kullanılır. Birincil olarak çağrılabilir imzalarda kullanılır.
  İki nokta üst üste her zaman bir tür imzası oluşturduğundan, 0,3'te oluşturulan üç koşullu işleç true ve false değerlerini ayırmak için bir dikey çubuk (`|`) kullanır. Bu nedenle Q#, C'de olduğu gibi ayırıcı olarak iki nokta üst üste yerine `cond ? tval | fval` kullanır.
  
