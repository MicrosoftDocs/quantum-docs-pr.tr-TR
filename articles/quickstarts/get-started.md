---
uid: microsoft.quantum.welcome
title: Quantum Development Kit'i (QDK) kullanmaya başlama
description: Microsoft Quantum geliştirme setiyle Q# dilinde kuantum projelerini programlamaya nasıl başlayacağınızı öğrenin.
author: bradben
ms.author: bradben
ms.date: 5/10/2020
ms.topic: overview
no-loc:
- Q#
- $$v
ms.openlocfilehash: ff5eb9984da0b22a65f3919599ee18605a206fa0
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867531"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>Quantum Development Kit'i (QDK) kullanmaya başlama

Microsoft Quantum Development Kit'e hoş geldiniz!  

Quantum geliştirme seti (QDK), özellikle kuantum uygulamaları geliştirmek üzere tasarlanan bir programlama dili olan Q# ile kendi kuantum programlarınızı ve denemelerinizi oluşturmak için ihtiyacınız olan tüm araçları içerir.

[QDK yükleme kılavuzu](xref:microsoft.quantum.install) ile hemen başlayın.
Bu kılavuzda, kendi kuantum programlarınızı yazabilmeniz için Quantum geliştirme setini Windows, Linux veya MacOS makinelere yükleme rehberliği alacaksınız.

Kuantum bilişimi konusunda yeniyseniz, kuantum bilgisayarların neler yapabileceğini ve kuantum bilişimi ile ilgili temel bilgileri öğrenmek için [Genel bakış](xref:microsoft.quantum.overview.introduction) bölümünü gözden geçirin.

## <a name="get-started-programming"></a>Programlamaya başlayın

Quantum geliştirme seti, Q# ile kuantum programı geliştirmeyi öğrenmek için birçok yol sunar.
Kuantumun gücünden yararlanmaya başlamak için öğreticilerimizi deneyebilirsiniz:

* [Kuantum rastgele sayı oluşturucusu](xref:microsoft.quantum.quickstarts.qrng): Kuantum kavramlarına yönelik kısa bir tanıtım sağlarken aynı zamanda birkaç dakika içinde bir kuantum uygulaması oluşturup çalıştırmanıza olanak tanıyan "Q# Merhaba Dünya" stilinde bir uygulama ile başlayın.
* [Q# ile dolaşıklığı keşfetme](xref:microsoft.quantum.write-program): Bu öğretici, kuantum programlamanın bazı temel kavramlarını gösteren bir Q# programı yazma adımlarında size rehberlik eder.
    Kodlamaya başlamaya hazır değilseniz, yine de QDK'yi yüklemeden anlatımı takip ederek Q# programlama diline genel bir bakış elde edebilir ve kuantum bilişiminin ilk kavramlarını öğrenebilirsiniz.
* [Grover arama algoritması](xref:microsoft.quantum.quickstarts.search): Kuantum algoritmasına alt düzey kuantum işlemlerini soyutlama açısından yaklaşan ve Q# dilinin gücü hakkında fikir edinmenizi sağlayan bu Q# programı örneğini keşfedin.
    Bu öğretici, Visual Studio veya Visual Studio Code kullanarak programı bir Q# komut satırı uygulaması olarak geliştirme sürecinde size rehberlik eder.

### <a name="learning-further"></a>Daha fazlasını öğrenme
* [Kuantum bilişimi için Microsoft Learn modülleri](https://docs.microsoft.com/learn/browse/?term=quantum), temel kavramlar konusunda size uygun hızda ve zamanda ustalaşmayı öğretir. [İlk modülümüzü](https://docs.microsoft.com/learn/modules/qsharp-create-first-quantum-development-kit/) kullanarak QDK ile kuantum programlarının nasıl oluşturulacağı ile ilgili temel bilgileri öğrenebilirsiniz.
* Q# programlama hakkında daha ayrıntılı bilgi edinmek istiyorsanız Q# dilinde programlama alıştırmaları aracılığıyla kuantum bilişimini tanıtan ve kendi hızınızda ilerleyebileceğiniz bir alıştırma koleksiyonu olan [Quantum Katalarına](https://github.com/Microsoft/QuantumKatas) göz atın.
    Bu kataların çoğu ayrıca Q# Not Defterleri olarak da sunulur. 
* [Örnek depomuzda](https://github.com/Microsoft/Quantum), Q# kullanarak kuantum programları yazmaya yönelik çok sayıda örnek bulunur. Bu örneklerin çoğu, [standart](xref:microsoft.quantum.libraries.standard.intro) ve [kimya](xref:microsoft.quantum.chemistry.concepts.intro) kitaplıkları dahil açık kaynak [kuantum kitaplıklarımız](https://github.com/Microsoft/QuantumLibraries) kullanılarak yazılmıştır. (Aşağıda bu konu hakkında daha fazla bilgi bulabilirsiniz.)

## <a name="key-concepts-for-quantum-computing"></a>Kuantum bilişimine yönelik temel kavramlar

Kuantum geliştirmeye yeni başladıysanız tüm bunların biraz kafa karıştırıcı olabileceğinin farkındayız. Bu temel kavramlar, kuantum dünyasına adım atmanıza ve kuantum bilişiminin hangi bakımlardan klasik bilişimden farklı olduğunu anlamanıza yardımcı olmak için tasarlanmıştır.

* [Kuantum bilişimini anlama](xref:microsoft.quantum.overview.understanding)
* [Kuantum bilgisayarlar ve kuantum simülatörleri](xref:microsoft.quantum.overview.simulators)
* [Q# programlama dili ve QDK nedir?](xref:microsoft.quantum.overview.q-sharp)
* [Kuantum bilişimi için doğrusal cebir](xref:microsoft.quantum.overview.algebra)

## <a name="quantum-development-kit-documentation"></a>Quantum Geliştirme Seti Belgeleri

Geçerli belge aşağıdaki ek konuları içerir.

### <a name="no-locq-developer-guides"></a>Q# geliştirici kılavuzları

* [Q# Kullanıcı Kılavuzu](xref:microsoft.quantum.guide), Q# dilinde kuantum programları oluşturmak için kullanılan temel kavramları ayrıntılı olarak açıklar.
* [Kuantum simülatörleri ve konak uygulamaları](xref:microsoft.quantum.machines), kuantum algoritmalarının yürütülme şeklini, hangi kuantum makinelerinin kullanılabilir olduğunu ve kuantum programı için Q# dışı bir sürücü yazmayı açıklar.

### <a name="no-locq-libraries"></a>Q# kitaplıkları

* [Q# standart kitaplıkları](xref:microsoft.quantum.libraries.standard.intro), hem klasik dil denetimi gereksinimini hem de Q# kuantum algoritmalarını destekleyen işlemleri ve işlevleri açıklar. 
    Denetim akışı, veri yapıları, hata düzeltme, test ve hata ayıklama konularını içerir. 
* [Q# kimya kitaplığı](xref:microsoft.quantum.chemistry.concepts.intro), kuantum bilişiminin kritik bir uygulaması olan kuantum kimya simülasyonunu destekleyen işlemleri ve işlevleri açıklar. Hamiltonian dinamiği simülasyonu, kuantum aşama tahmini ve diğer konuları içerir.
* [Q# sayısal kitaplığı](xref:microsoft.quantum.numerics.intro), hedef makinelerin yerel işlemleri açısından karmaşık aritmetik işlevleri ifade etmeyi destekleyen işlemleri ve işlevleri açıklar.
* [Q# kitaplık başvurusu](xref:microsoft.quantum.standardlibsintro), ad alanına göre kitaplık varlıkları hakkında başvuru bilgileri içerir.

### <a name="general-quantum-computing"></a>Genel kuantum bilişimi

* [Kuantum bilişimi kavramları](xref:microsoft.quantum.concepts.intro), doğrusal cebirin kuantum bilişimindeki yeri, qubit’lerin doğası ve kullanımı, kuantum bağlantı hattını okuma ve diğer konuları içerir.
* [Kuantum bilişimi sözlüğü](xref:microsoft.quantum.glossary), kuantum bilişimine ve program geliştirmeye özgü bazı önemli terimleri içeren bir sözlüktür.
    Bu alanda yeniyseniz, belgelerimizi okurken bu sözlük kullanışlı bir başvuru olabilir.
* [Daha fazla bilgi](xref:microsoft.quantum.more-information), kuantum bilişimi konularının ayrıntılı olarak incelenmesi için özel olarak seçilen başvuruları içerir.

### <a name="additional-info"></a>Ek bilgiler

* [Microsoft Quantum Geliştirme Seti sürüm notları](xref:microsoft.quantum.relnotes).


## <a name="be-a-part-of-the-no-locq-open-source-community"></a>Q# Açık Kaynak Topluluğu’nun bir parçası olun

Quantum Geliştirme Seti, dünyanın en önemli sorunlarını çözebilmemiz için geliştiricilerin kuantum bilişimini herkes için daha erişilebilir yapmasına yardımcı olan bir açık kaynak geliştirme setidir.  Açık kaynak yazılım gerektiren akademik kurumlar, kendi kuantum öğrenme ve geliştirme çalışmaları için Q# dilini dağıtabilir. Geliştirme setinin açık kaynak olması ayrıca geliştiricilere ve etki alanı uzmanlarına, kodları aracılığıyla iyileştirme ve fikir katkısında bulunma fırsatı sunar.

Quantum Geliştirme Seti’ne yönelik geri bildiriminiz, katılımınız ve katkılarınız önemlidir.  Quantum Geliştirme Seti kaynakları hakkında daha fazla bilgi edinmek, geri bildirim sağlamak, kararlara nasıl katılabileceğinizi ve büyüyen bu kuantum geliştirme platformuna nasıl katkıda bulunabileceğinizi öğrenmek için bkz. [Quantum Geliştirme Seti’ne katkı yapma](xref:microsoft.quantum.contributing).

Microsoft’un kuantum bilişimi girişimi hakkında daha fazla genel bilgi almak istiyorsanız bkz. [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/).
