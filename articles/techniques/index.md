---
title: Quantum geliştirme teknikleri
description: Q# program geliştirmenin temellerini öğrenin, işlemlerle, işlevlerle, değişkenlerle ve qubit’lerle çalışın ve basit bir kuantum programı oluşturun.
keywords: SEO uzmanınıza danışmadan anahtar sözcük eklemeyin veya anahtar sözcükleri düzenlemeyin.
author: QuantumWriter
ms.author: MSFT-alias-person-or-DL
ms.date: 9/20/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.techniques.intro
ms.openlocfilehash: e5b7fbde18afbc0333d89f70c5e4596848e30f4f
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907724"
---
# <a name="quantum-development-techniques"></a>Quantum Geliştirme Teknikleri

Belgelerimizin bu bölümünde, Q# dilinde kuantum programları oluşturmak ve klasik uygulamalardan bu programlarla etkileşimde bulunmak için kullanılan temel kavramlar ayrıntılı olarak açıklanmıştır.
[Kuantum bilgi işlem kavramları](xref:microsoft.quantum.concepts.intro) bölümünde açıklananlar gibi *bazı* bilgilere sahip olduğunuz varsayılır ancak bu bölümlerden yararlanmak için bir kuantum bilgi işlem uzmanı olmanız gerekmez.

İçerikleri aşağıdaki gibidir.

- [Q# programına genel bakış](xref:microsoft.quantum.techniques.file-structure), Q# programlama dilinin amacı ve işlevlerine yönelik genel bir bakış sağlar. 
    Özellikle, Q#’ın yalnızca kuantum mekaniğinin simülasyonunu yapmaya yönelik bir dil *olmadığını* açıklar. (Yine de bu işlevsellik tam durum simülatörümüz tarafından sağlanır.) 
    Bunun yerine, Q# geleceğe yönelik olarak tasarlanmıştır ve programları klasik bir denetim bilgisayarının qubit’lerle nasıl *etkileşime girdiğini* açıklar. 

- [İşlemler ve işlevler](xref:microsoft.quantum.techniques.opsandfunctions), Q# dilinin çağrılabilir iki türü hakkında ayrıntılar sağlar: *işlemler*, qubit’ler ve kuantum sistemleri üzerindeki eylemleri içerir ve *işlevler*, yalnızca klasik bilgilerle çalışır. 
    Klasik ve kuantum bilgileri birlikte çalışmadan kuantum bilgi işlem gerçekleştirilemez. 
    Bu bölümde, bu çağrılabilir öğelerin bir Q# programının denetim akışı içinde nasıl tanımlanacağı ve kullanılacağı açıklanmaktadır.

- [Yerel değişkenler](xref:microsoft.quantum.techniques.local-variables), Q# programlarındaki değişkenlerin rolünü ve bunların nasıl etkili bir şekilde kullanılacağını açıklar. 
    Özellikle, sabit/değişebilir değişkenler arasındaki farkı ve bunları nasıl atayacağınızı/yeniden atayacağınızı öğreneceksiniz.

- [Qubit’ler ile çalışma](xref:microsoft.quantum.techniques.qubits), tek başına qubit’lere ve qubit sistemlerine yönelik olarak kullanabileceğiniz Q# özelliklerini açıklar. 
    Özellikle, bunların ayrılmasını, bunlara yönelik işlemler gerçekleştirmeyi ve son olarak ölçülerini kapsar. 
    Ayrıca, bazı faydalı denetim akışı tekniklerini öğreneceksiniz.

- [Hepsini bir araya getirme](xref:microsoft.quantum.techniques.puttingittogether) bölümünde, **kuantum teleportasyonu** (tam durumu bir qubit’ten diğerine "teleport" etmek için iki klasik bit kullanma) gerçekleştiren bir program oluşturmak üzere yukarıdaki bölümlerde öğrendiğiniz teknikleri kullanacaksınız.

- [Daha fazlası](xref:microsoft.quantum.techniques.going-further) bölümü, daha karmaşık kuantum programlamaya doğru ilerlerken yararlı olabilecek gelişmiş teknikler sunar. 
    Özellikle, Q# içinde, belirli giriş/çıkış türlerinden bağımsız kalarak daha yüksek düzeyli denetim akışı sağlayan ve qubit’leri *ödünç alan* *tür parametreli* işlemlerin ve işlevlerin kullanımı incelenmektedir. 
    İkincisi, bir Q# işleminin, hesaplamalar konusunda yardımcı olmak için bilinen bir duruma başlatılması gerekmeyen "kirli" qubit’leri kullanabildiği için temel qubit ayırmasından farklıdır.

- [Test ve hata ayıklama](xref:microsoft.quantum.techniques.testing-and-debugging) bölümünde, kodunuzun doğru şekilde çalıştığından emin olmaya yönelik bazı teknikler açıklanır. 
    Kuantum bilgilerinin genel opaklığı nedeniyle, bir kuantum programında hata ayıklamak için özel teknikler gerekebilir. 
    Neyse ki, Q# kuantuma özgü tekniklerin yanı sıra klasik hata ayıklama tekniklerinin birçoğunu destekler. Bunlar Q# içinde birim testi oluşturmayı/çalıştırmayı, kodunuzda değerlere ve olasılıklara *onay deyimi* eklemeyi ve hedef makine durumunun çıkışını oluşturan `Dump` işlevlerini içerir. 
    Sonuncusu, bazı kuantum sınırlamalarını (ör. kopyalamama teoremi) atlayarak işlemlerin belirli bölümlerinde hata ayıklamak için tam durum simülatörümüzle birlikte kullanılabilir.


![Kuantum](~/media/mobius_strip_preview.png)
