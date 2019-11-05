---
title: Q# ile kuantum bilişimi nasıl öğrenilir?
description: ''
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.learn
ms.openlocfilehash: 8967fee11931c6cef4b2d98084b2e319cea55284
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444115"
---
# <a name="how-to-learn-quantum-computing"></a>Kuantum bilişimi nasıl öğrenilir?

Kuantum bilişimi hakkında bilgi edinmek ve ilk programlarınızı yazmak için rehberlik alın. Bu çok kapsamlı bir kılavuz değildir, yalnızca iyi bir başlangıç sağlar.

## <a name="getting-started-overview"></a>Kullanmaya Başlama genel bakışı

[Microsoft Quantum Development Kit'i kullanmaya başlama](xref:microsoft.quantum.welcome) belgesinde ilk Q# programınızı yazmak için kullanabileceğiniz öğreticiler, kullanmaya başlama kılavuzları ve kuantum programı geliştirmek için kullanabileceğiniz Q# kuantum kitaplıkları hakkında temel bilgiler gibi Q# ile kuantum bilişimiyle ilgili genel bakış sağlanmaktadır.

## <a name="learning-the-basics-what-do-you-need-to-know"></a>Temel bilgileri öğrenme: Ne bilmeniz gerekiyor?

Q# dilini ve kuantum bilişimini öğrenmek veya kuantum uygulamaları yazmaya başlamak için kuantum fiziği bilmeniz gerekmez.

Bu kavramlar kuantum programları kodlamaya başlarken ihtiyacınız olacak temel bilgiye iyi bir giriş yapmanızı sağlar.  

* [Temel kuantum mekaniği](xref:microsoft.quantum.concepts.intro): Az önce kodlamaya başlamak için kuantum fiziği bilmenizin gerekmediğini belirtmiştik (ki bu doğru!). Ama kuantum mekaniğinin bazı temel kavramları ve matematiksel gösterimi, kuantum programlamayı anlamanıza yardımcı olacaktır.

* **Doğrusal cebir (vektörler ve matrisler)** : Kuantum bilişiminde, kuantum durumları vektörlerle temsil edilir ve kuantum işlemleri de bu vektörlere uygulanan doğrusal dönüşümlerdir.  [Doğrusal Cebir hakkında Jupyter Notebook öğreticisini](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra) inceleyebilirsiniz.  Dilerseniz bu konu hakkında daha fazla bilgi için [vektörler ve matrisler](xref:microsoft.quantum.concepts.vectors) kavram kılavuzumuza bakabilirsiniz.

* **Kompleks aritmetik**: Kuantum durumu vektörlerinin katsayıları karmaşık sayılardır. Bazı temel kuantum bilişimi kavramlarını bunlar olmadan da anlayabilirsiniz ama bunları kuantum araç setinize ekleme ihtiyacı duymadan fazla ileri gidemezsiniz.  [Bu kompleks aritmetik hakkında Jupyter Notebook öğreticisinde](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic) kuantum bilişimi ile çalışmak için gerekli olan bazı matematiksel arka plan bilgileri anlatılmaktadır. 

Artık temel bilgilere sahip olduğunuza göre kuantum programı yazmaya başlamak için hazırsınız.  İlerlemek için tercih edebileceğiniz birçok yol vardır:

## <a name="do-the-quantum-katas"></a>Kuantum Katalarını tamamlama

[Kuantum Kataları](xref:microsoft.quantum.overview.katas), size aynı anda hem kuantum bilişiminin hem de Q# programlamanın öğelerini öğretmeyi amaçlayan, kendi hızınızda ilerleyebileceğiniz bir açık kaynak öğretici serimizdir.  Her bir katada o katayı başarılı bir şekilde tamamlayabilmek için ihtiyaç duyulan kuantum bilişimi kavramlarını öğrenmek için kullanabileceğiniz ek öğrenme materyalleri mevcuttur.  

## <a name="dive-into-the-theory"></a>Teoriye dalma

Kuantum mekaniği ve kuantum bilişimi teorisine daha ayrıntılı bakmak istiyor olabilirsiniz. Burada yararlı malzemelerin listesi verilmiştir:

* Kuantum bilişiminin temel kavramlarının derlendiği [kuantum bilişimi kavramları](xref:microsoft.quantum.concepts.intro) kılavuzumuzla başlayın.
* _Learn Quantum Computing with Python and Q#_ ([Python ve Q# ile Kuantum Bilişimini Öğrenme] Sarah C. Kaiser ve Christopher E. Granade), kuantum mekaniğiyle ilgili çok kısıtlı deneyimi olan veya hiç olmayan ama biraz programlama geçmişi olan kişilere yönelik giriş niteliğinde mükemmel bilgileri sağlar.
* _Quantum Computation and Quantum Information_ ([Kuantum Hesaplama ve Kuantum Bilgileri] Michael A. Nielsen, Isaac L. Chuang), kuantum hesaplama alanında en çok alıntı yapılan metindir. Konunun standart metni olarak kabul edilir. Kitapta okuyucunun kuantum mekaniği ve bilgisayar bilimiyle ilgili minimum düzeyde ön deneyimi olduğu varsayılır. Hem konuya sıkı bir giriş yapmak isteyen hem de gelişmiş kavramlara başvurular bulmak isteyen okuyucular için harika bir seçimdir.
* MIT OpenCourseWare'in, kuantum mekaniğinin temellerini öğrenmek isteyenlere yönelik olan ve Allan Adams tarafından verilen harika bir [çevrimiçi kursu](https://www.youtube.com/watch?v=lZ3bPUKo5zc&list=PLUl4u3cNGP61-9PEhRognw5vryrSEVLPr) vardır. Telem fiziği daha iyi anlamak isteyenler için çok uygundur.

## <a name="join-the-quantum-community"></a>Kuantum topluluğuna katılın

Bunu tek başınıza öğrenmeniz gerekmez; size yardım etmeye gönüllü olacak amatörler ve uzmanlardan oluşmuş büyük bir topluluk vardır. Sormaktan korkmayın!

* Q# ve kuantum bilişimi hakkında sorularınız varsa hiç tereddüt etmeyin ve Quantum Computing StackExchange sitesine bir göz atın. Sorunuzu orada bulamazsanız, her zaman yeni bir soru sorabilirsiniz. 
* Q# ile ilgili en son haberleri ve kaynakları yakından izlemek için [Q# blogunu](https://devblogs.microsoft.com/qsharp/) ve [Microsoft Quantum Blogunu](https://cloudblogs.microsoft.com/quantum/) gözden geçirin.
* Daha fazla kaynak ve malzeme aramak için [Q# Topluluğu](https://qsharp.community/) ve [Awesome Q#](https://project-awesome.org/ebraminio/awesome-qsharp) adreslerine bakın.

 Kuantum bilişimi hakkında ders vermek istiyorsanız [Microsoft Quantum Network](https://info.microsoft.com/LearnMoreAboutMicrosoftQuantumNetwork.html), müfredat konusunda size yardımcı olabilir.  

