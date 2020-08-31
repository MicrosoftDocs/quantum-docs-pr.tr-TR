---
title: Q# programlama dili ve QDK nedir?
description: Microsoft Quantum geliştirme seti, Q# programlama dili ve kuantum programları oluşturma hakkında bilgi edinin.
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.q-sharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5db574b0380ffa1616cb3959d84925854df4e321
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863787"
---
# <a name="what-are-the-no-locq-programming-language-and-qdk"></a>Q# programlama dili ve QDK nedir?

Q#, Microsoft'un kuantum algoritmaları geliştirmeye ve çalıştırmaya yönelik açık kaynak programlama dilidir. Bu, [Q# kitaplıklarını](xref:microsoft.quantum.libraries), [kuantum simülatörlerini](xref:microsoft.quantum.machines), [diğer programlama ortamlarına yönelik uzantıları](xref:microsoft.quantum.install) ve [API belgelerini](xref:microsoft.quantum.standardlibsintro) içeren Quantum geliştirme setinin (QDK) bir parçasıdır. QDK, Standart Q# kitaplığına ek olarak Kimya, Makine Öğrenmesi ve Sayısal kitaplıklarını da içerir.

Q#, bir programlama dili olarak Python, C# ve F# dillerindeki alışıldık öğeleri kullanır ve döngüler, if/then deyimleri ve ortak veri türleri içeren programlar yazmak için temel bir yordamsal modeli destekler. Ayrıca kuantum odaklı yeni veri yapıları ve işlemleri sunar.

## <a name="what-can-i-do-with-the-qdk"></a>QDK ile ne yapabilirim?

QDK, çeşitli ortamlarda çalıştırabileceğiniz kuantum uygulamaları geliştirmek için ortak araçlar ve dillerle kullanabileceğiniz, Q# diline yönelik tam özellikli bir geliştirme setidir. Q# programları Jupyter Not Defterleri aracılığıyla bir konsol uygulaması olarak çalışabilir veya bir Python ya da .NET konak programı kullanabilir.

### <a name="develop-in-common-tools-and-environments"></a>Ortak araçlarda ve ortamlarda geliştirme

[Visual Studio, Visual Studio Code](xref:microsoft.quantum.install.standalone) ve [Jupyter Not Defterleri](xref:microsoft.quantum.install.jupyter) ile kuantum geliştirmenizi tümleştirin. [Python](xref:microsoft.quantum.install.python) ve [.NET](xref:microsoft.quantum.install.cs) konak dilleri ile programlarınızı eşleştirmek için yerleşik API’leri kullanın.

### <a name="try-quantum-operations-and-domain-specific-libraries"></a>Kuantum işlemlerini ve etki alanına özel kitaplıkları deneme

Süper konum, dolaşıklık ve diğer kuantum işlemlerini keşfetmek için kuantum algoritmaları yazın ve test edin. Q# kitaplıkları, alt düzey işlem dizileri tasarlamak zorunda kalmadan karmaşık kuantum işlemleri çalıştırmanızı sağlar.

### <a name="run-programs-in-simulators"></a>Simülatörlerde program çalıştırma

Kuantum programlarınızı tam durumlu bir kuantum simülatöründe veya sınırlı kapsama sahip bir Toffoli simülatöründe çalıştırın ya da Q# kodunuzu farklı kaynak tahmin araçlarında test edin. 

## <a name="where-can-i-learn-more"></a>Nereden daha fazla bilgi edinebilirim?

|||
| ---- | ---- |
| **Kuantum bilişiminde yeniyim** | [Temel Kavramlar](xref:microsoft.quantum.overview.understanding) bölümünde kuantum fiziği ve kuantum bilişimi ile ilgili bazı temel bilgileri gözden geçirin.|
| **Q# dilini daha ayrıntılı olarak incelemek istiyorum** | [Q# Kullanıcı Kılavuzu](xref:microsoft.quantum.guide)’nda türleri, ifadeleri, değişkenleri ve kuantum program yapısını keşfedin.|
| **Yalnızca kuantum programları yazmaya başlamak istiyorum** | [Hızlı Başlangıçlar](xref:microsoft.quantum.install)’da Q# ortamınızı ayarlayın ve kuantum programları yazmaya başlayın.|

## <a name="how-does-no-locq-work"></a>Q# nasıl çalışır?

Q# programı, bağımsız bir uygulama olarak derlenebilir veya Python ya da bir .NET dilinde yazılmış konak programı tarafından çağrılabilir.

Programı derleyip çalıştırdığınızda, bir kuantum simülatörü örneği oluşturur ve Q# kodunu buna geçirir. Simülatör, Q# kodunu kullanarak kubitler (kuantum parçacıklarının simülasyonları) oluşturur ve bu kubitlerin durumlarını değiştirmek için dönüştürme işlemleri uygular. Ardından simülatördeki kuantum işlemlerinin sonuçları programa döndürülür.  

Q# kodunu simülatörde yalıtmak, algoritmaların kuantum fiziği yasalarını izlemesini ve kuantum bilgisayarlarda doğru şekilde çalışmasını sağlar.

![qsharp-code-flow](~/media/qsharp-code-flow.png)

## <a name="how-do-i-use-the-qdk"></a>QDK’yi nasıl kullanırım?

Q# derleyicisi, Q# kitaplıkları ve kuantum simülatörleri de dahil olmak üzere Q# programları yazmak ve çalıştırmak için ihtiyacınız olan her şey yerel bilgisayarınızdan yüklenip çalıştırılabilir. Gelecekte Q# programlarınızı gerçek bir kuantum bilgisayarda uzaktan çalıştırabileceksiniz, ancak o zamana kadar QDK ile birlikte sunulan kuantum simülatörleri doğru ve güvenilir sonuçlar sağlar.

- [Q# uygulamaları](xref:microsoft.quantum.install.standalone) geliştirmek, kullanmaya başlamanın en hızlı yoludur.

- Q# programlarını derlemeye, görselleştirmeye ve bunların simülasyonunu yapmaya yönelik bir Jupyter uzantısı olan bağımsız ve [IQ# içeren Jupyter Not Defterlerini](xref:microsoft.quantum.install.jupyter) çalıştırın.

- [Python](xref:microsoft.quantum.install.python) hakkında bilgi sahibiyseniz kullanmaya başlamak için bunu bir konak programlama platformu olarak kullanabilirsiniz. Python, yalnızca geliştiriciler arasında değil aynı zamanda bilim insanları, araştırmacılar ve öğretmenler arasında da yaygın olarak kullanılır.

- [C#, F# veya VB.NET](xref:microsoft.quantum.install.cs) deneyiminiz varsa ve Visual Studio geliştirme ortamı hakkında bilgi sahibiyseniz Visual Studio’yu Q# diline hazırlamak için buna eklemeniz gereken yalnızca birkaç uzantı vardır.  

## <a name="summary"></a>Özet

Q#, kuantum programları geliştirmeye yönelik açık kaynak bir programlama dilidir. Karmaşık kuantum işlemleri oluşturmanızı sağlayan kitaplıklara ve programlarınızı doğru bir şekilde çalıştırıp test etmenizi sağlayan kuantum simülatörlerine sahiptir. Q# programları bağımsız uygulamalar olarak çalıştırılabilir veya bir Python ya da .NET konak programından çağrılabilir ve ayrıca yerel bilgisayarınızdan yazılabilir, çalıştırılabilir ve test edilebilir.

## <a name="next-steps"></a>Sonraki Adımlar

[Kuantum bilişimi için doğrusal cebir](xref:microsoft.quantum.overview.algebra)
