---
uid: microsoft.quantum.welcome
title: Quantum Development Kit'i (QDK) kullanmaya başlama
description: QDK'yı kullanmaya başlamayı öğrenin.
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: overview
ms.openlocfilehash: 066981e3e2fb468c1ff2a4cf4d3e7cff057772ab
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036347"
---
# <a name="get-started-with-the-quantum-development-kit-qdk"></a>Quantum Development Kit'i (QDK) kullanmaya başlama

Microsoft Quantum Development Kit'e hoş geldiniz!  
QDK, kuantum uygulama geliştirme için özellikle tasarlanan bir programlama dili olan Q# ile kendi kuantum programlarınızı ve denemelerinizi oluşturmak için ihtiyacınız olan tüm araçları içerir. 

Hemen başlamak için [QDK yükleme kılavuzuna](xref:microsoft.quantum.install) gidebilirsiniz.
Bu kılavuzda, kendi kuantum programlarınızı yazmak için Quantum Geliştirme Seti’ni Windows, Linux veya MacOS makinelere yükleme rehberliği alırsınız.

Kodlamaya başlamak için tam olarak hazır değilseniz ancak kuantum bilişimi ile Q# hakkında daha fazla bilgi edinmek istiyorsanız, kullanabileceğiniz kaynaklar hakkında fikir edinmek için bu makaleyi yine de okumanız önerilir. [Kuantum bilişimi hakkında beş soru](#five-questions-about-quantum-computing) bölümünde, aradığınız her şey için bağlantılar bulabilirsiniz!

## <a name="get-started-programming"></a>Programlamaya başlayın

Quantum Geliştirme Seti, Q# ile kuantum programı geliştirmeyi öğrenmek için birçok yol sunar.
Kuantumun gücünden yararlanmaya başlamak için *hızlı başlangıçlarımızı* deneyebilirsiniz:

* [Kuantum rastgele sayı oluşturucusu](xref:microsoft.quantum.quickstarts.qrng), "Q# Merhaba Dünya" stilinde bir uygulamadır. Kuantum kavramlarına yönelik kısa bir tanıtım sağlarken aynı zamanda birkaç dakika içinde bir kuantum uygulaması oluşturup çalıştırmanıza olanak tanır.
* [Q# ile kuantumun temelleri](xref:microsoft.quantum.write-program), kuantum programlamanın bazı temel kavramlarını gösteren bir Q# programı yazma adımlarında size rehberlik yapar. 
    Kodlamaya başlamaya hazır değilseniz, yine de QDK'yi yüklemeden anlatımı takip ederek Q# bilgisayar diline genel bir bakış elde edebilir ve kuantum bilişiminin ilk kavramlarını öğrenebilirsiniz.
* [Grover arama algoritması](xref:microsoft.quantum.quickstarts.search), kuantum algoritmasına düşük düzeyli kuantum işlemlerini soyutlama açısından yaklaşan ve Q# dilinin gücü hakkında bilgi sahibi olmanızı sağlayan bir Q# programı örneği sunar. 
    Bu hızlı başlangıç, çeşitli programlama ortamlarını (Python konağıyla veya .NET dil konağıyla ve Visual Studio ya da Visual Studio Code ile) kullanarak program geliştirmeniz için size yol gösterir.

### <a name="learning-further"></a>Daha fazlasını öğrenme
* Q# programlama hakkında daha ayrıntılı bilgi edinmek istiyorsanız, Q# içinde programlama alıştırmaları aracılığıyla kuantum bilişimini tanıtan ve kendi hızınızda ilerleyebileceğiniz bir alıştırma koleksiyonu olan [Quantum Katas](https://github.com/Microsoft/QuantumKatas)’a göz atın.
    Bu kata’ların çoğu ayrıca Q# Not Defterleri olarak da sunulur. 
* [Örnek depomuzda](https://github.com/Microsoft/Quantum), Q# kullanarak kuantum programları yazmaya yönelik çok sayıda örnek bulunur. Bu örneklerin çoğu, [standart](xref:microsoft.quantum.libraries.standard.intro) ve [kimya](xref:microsoft.quantum.chemistry.concepts.intro) kitaplıkları dahil açık kaynak [kuantum kitaplıklarımız](https://github.com/Microsoft/QuantumLibraries) kullanılarak yazılmıştır. (Aşağıda bu konu hakkında daha fazla bilgi bulabilirsiniz.)

## <a name="five-questions-about-quantum-computing"></a>Kuantum bilişimi hakkında beş soru

Kuantum geliştirmeye yeni başladıysanız tüm bunların biraz kafa karıştırıcı olabileceğinin farkındayız. Kuantum bilişimi hakkında bilgi edinmeye başlamanıza yardımcı olacak kaynaklar sunuyoruz. Bu kısa makalelerin yardımıyla, kısa bir süre içinde programlamaya başlayacaksınız.
* [Kuantum bilişimi nedir?](xref:microsoft.quantum.overview.what)
* [Kuantum bilgisayarlar ne yapabilir?](xref:microsoft.quantum.overview.computers)
* [Kuantum bilişimini neden öğrenmeliyim?](xref:microsoft.quantum.overview.why)
* [Q# nedir?](xref:microsoft.quantum.overview.qsharp)
* [Q# ile kuantum bilişimi nasıl öğrenilir?](xref:microsoft.quantum.overview.learn)

## <a name="quantum-development-kit-documentation"></a>Quantum Geliştirme Seti Belgeleri

Geçerli belge aşağıdaki ek konuları içerir.

### <a name="using-q"></a>Q# kullanma
* [Kuantum geliştirme teknikleri](xref:microsoft.quantum.techniques.intro), Q# içinde kuantum programları oluşturmak için kullanılan temel kavramları belirtir. Konular dosya yapılarını, işlemleri ve işlevleri, qubit’lerle çalışmayı ve bazı gelişmiş konuları içerir.
* [Q# dil başvurusu](xref:microsoft.quantum.language.intro), tür modeli, ifadeler, deyimler ve derleyici kullanımı dahil Q# dilinin ayrıntılarını içerir.
* [Kuantum simülatörleri ve konak uygulamaları](xref:microsoft.quantum.machines), kuantum algoritmalarının yürütülme şeklini, hangi kuantum makinelerinin kullanılabilir olduğunu ve kuantum programı için Q# dışı bir sürücü yazmayı açıklar.

### <a name="q-libraries"></a>Q# kitaplıkları
* [Q# standart kitaplıkları](xref:microsoft.quantum.libraries.standard.intro), hem klasik dil denetimi gereksinimini hem de Q# kuantum algoritmasını destekleyen işlemleri ve işlevleri açıklar. 
    Denetim akışı, veri yapıları, hata düzeltme, test ve hata ayıklama konularını içerir. 
* [Q# kimya kitaplığı](xref:microsoft.quantum.chemistry.concepts.intro), kuantum bilişiminin kritik bir uygulaması olan kuantum kimya simülasyonunu destekleyen işlemleri ve işlevleri açıklar. Hamiltonian dinamiği simülasyonu, kuantum aşama tahmini ve diğer konuları içerir.
* [Q# nümerik kitaplığı](xref:microsoft.quantum.numerics.intro), hedef makinelerin yerel işlemleri açısından karmaşık aritmetik işlevleri ifade etmeyi destekleyen işlemleri ve işlevleri açıklar.
* [Q# kitaplık başvurusu](xref:microsoft.quantum.standardlibsintro), ad alanına göre kitaplık varlıkları hakkında başvuru bilgileri içerir.

### <a name="general-quantum-computing"></a>Genel kuantum bilişimi
* [Kuantum bilişimi kavramları](xref:microsoft.quantum.concepts.intro), doğrusal cebirin kuantum bilişimindeki yeri, qubit’lerin doğası ve kullanımı, kuantum bağlantı hattını okuma ve diğer konuları içerir.
* [Kuantum bilişimi sözlüğü](xref:microsoft.quantum.glossary), kuantum bilişimine ve program geliştirmeye özgü bazı önemli terimleri içeren bir sözlüktür. 
    Bu alanda yeniyseniz, belgelerimizi okurken bu sözlük kullanışlı bir başvuru olabilir.
* [Daha fazla bilgi](xref:microsoft.quantum.more-information), kuantum bilişimi konularının ayrıntılı olarak incelenmesi için özel olarak seçilen başvuruları içerir.

### <a name="additional-info"></a>Ek bilgiler
* [Microsoft Quantum Geliştirme Seti sürüm notları](xref:microsoft.quantum.relnotes).


## <a name="be-a-part-of-the-q-open-source-community"></a>Q# Açık Kaynak Topluluğu’nun bir parçası olun
Quantum Geliştirme Seti, dünyanın en önemli sorunlarını çözebilmemiz için geliştiricilerin kuantum bilişimini herkes için daha erişilebilir yapmasına yardımcı olan bir açık kaynak geliştirme setidir.  Açık kaynak yazılım gerektiren akademik kurumlar, kendi kuantum öğrenme ve geliştirme çalışmaları için Q#’ı dağıtabilir. Geliştirme setinin açık kaynak olması ayrıca geliştiricilere ve etki alanı uzmanlarına, kodları aracılığıyla iyileştirme ve fikir katkısında bulunma fırsatı sunar.

Quantum Geliştirme Seti’ne yönelik geri bildiriminiz, katılımınız ve katkılarınız önemlidir.  Quantum Geliştirme Seti kaynakları hakkında daha fazla bilgi edinmek, geri bildirim sağlamak, kararlara nasıl katılabileceğinizi ve büyüyen bu kuantum geliştirme platformuna nasıl katkıda bulunabileceğinizi öğrenmek için bkz. [Quantum Geliştirme Seti’ne katkı yapma](xref:microsoft.quantum.contributing).

Microsoft’un kuantum bilişimi girişimi hakkında daha fazla genel bilgi almak istiyorsanız bkz. [Microsoft Quantum](https://www.microsoft.com/en-us/quantum/).
