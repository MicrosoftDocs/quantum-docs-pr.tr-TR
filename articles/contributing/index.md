---
title: Quantum Development Kit’e katkı yapma | Microsoft Docs
description: Quantum Development Kit’e katkı yapma
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing
ms.openlocfilehash: 4be86c5045ece62ae3af40090a2cd344d965e65f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035158"
---
# <a name="contributing-to-the-quantum-development-kit"></a>Quantum Development Kit’e katkı yapma #

Quantum Development Kit, kuantum programları yazmaya yönelik bir araç koleksiyonundan fazlasıdır.
Kuantum bilişimini keşfetmekte olan, kuantum algoritmalarında araştırma yapan, kuantum cihazlar için yeni uygulamalar geliştiren ve kuantum programlamadan en iyi şekilde yararlanmak için diğer şekillerde çalışan geniş bir insan topluluğunun parçasıdır.
Bu topluluğun bir parçası olarak Quantum Development Kit, kuantum geliştiricilerine ihtiyaç duydukları özelliklerle çok çeşitli arka planlar sunmayı amaçlamaktadır.
Quantum Development Kit’e yaptığınız katkılar, diğer kuantum geliştiriciler tarafından kullanılan araçları, bu araçların belgelenme yöntemlerini geliştirerek ve hatta tüm kuantum programlama topluluğunu keşfetmek ve içerik oluşturmak için daha iyi bir yer haline getirmeye yardımcı olan yeni özellik ve işlevler oluşturarak bu amacı gerçekleştirmeye yardımcı olur.
Nazik katkılarınız ve topluluğumuzu mümkün olan en iyi seviyeye getirirken birlikte çalışma fırsatı sunduğunuz için teşekkür ediyoruz.

Bu kılavuzda, katkınızın kuantum programlama topluluğuna mümkün olduğunca yarar olmasıyla ilgili bazı önerilerde bulunacağız.

## <a name="building-community"></a>Topluluk Oluşturma ##

Katkı yapmanın ilk adımı, katkıda bulunduğunuz topluluğu her zaman aklınızda bulundurmaktır.
Kuantum programlama topluluğundaki akranlarınıza ve diğer kişilere karşı saygılı ve profesyonel bir şekilde davranarak, çalışmalarınızın mümkün olan en iyi ve en samimi topluluğu inşa etmesine yardımcı olabilirsiniz.

Bu çabanın bir parçası olarak, tüm Quantum Development Kit projelerinde [Microsoft Açık Kaynak Davranış Kuralları](https://opensource.microsoft.com/codeofconduct/) benimsenmiştir.
Daha fazla bilgi için lütfen [Davranış Kuralları Hakkında SSS](https://opensource.microsoft.com/codeofconduct/faq/) konusuna bakın veya sorularınızı ya da görüşlerinizi bildirmek için [opencode@microsoft.com](mailto:opencode@microsoft.com) ile iletişime geçin.

## <a name="what-kinds-of-contributions-help-the-community"></a>Ne Tür Katkılar Topluluğa Yardımcı Olur? ##

Katkılarınızla kuantum programlama topluluğuna yardımcı olmanın birçok farklı yolu vardır.
Bu kılavuzda özellikle Kuantum Geliştirme Kiti ile ilgili olan üç yönteme odaklanacağız.
Bu yöntemlerin hepsi, kullanıcıları güçlendiren bir kuantum topluluğu inşa etmek için çok önemlidir.
Bununla birlikte, bu kesinlikle kapsamlı bir liste değildir. Topluluğun kuantum programlama taahhüdüyle gelişmesine yardımcı olacak başka yollar da keşfetmenizi öneririz!

- **Hataları raporlama.** Hataları ve diğer türlü sorunları düzeltmenin birinci adımı, bunları belirlemektir. Quantum Development Kit’te bir hata bulduysanız bize bildirmeniz düzeltmemize ve kuantum programlama topluluğu için daha iyi bir araç seti haline getirmemize yardımcı olur.
- **Belgeleri iyileştirme.** Bir belge kümesi her zaman daha iyi olabilir, daha fazla ayrıntıyı kapsayabilir ve daha erişilebilir hale getirilebilir.
- **Koda katkıda bulunma.** Elbette, katkıda bulunmak için en dolaysız yollardan biri Quantum Development Kit’e yeni kod eklemektir.

Bu farklı türdeki katkıların tümü çok değerlidir ve çok faydalı olacaktır.
Kılavuzun geri kalanında her bir katkı türü hakkında öneriler sunacağız.

## <a name="where-do-contributions-go"></a>Katkıları Nereye Gidiyor? ##

Quantum Development Kit, kuantum programları yazmaya yönelik bir platformu hayata geçirmek için hepsi birlikte çalışan birkaç farklı unsurdan oluşur.
Bu farklı parçaların her birinin ana unsuru farklı bir depoda bulunur; bu nedenle, ilk önce her katkının nereye ait olduğunu çözmek gerekir.

- [**microsoft/Quantum**](https://github.com/Microsoft/Quantum): Quantum Development Kit’i kullanmaya başlamanıza yardımcı olacak örnekler ve araçlar.
- [**microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries): Quantum Development Kit için standart ve etki alanına özel kitaplıklar.
- [**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas): Kuantum bilişimini ve Q# programlama dilini öğrenmeye yönelik, kendi hızınızda ilerleyebileceğiniz programlama alıştırmaları.
- [**microsoft/qsharp-compiler**](https://github.com/microsoft/qsharp-compiler): Q# derleyicisi, Visual Studio uzantısı ve Visual Studio Code uzantısı.
- [**microsoft/qsharp-runtime**](https://github.com/microsoft/qsharp-runtime): Quantum Development Kit için simülasyon çerçevesi, kod oluşturma ve simülasyon hedef makineleri.
- [**microsoft/iqsharp**](https://github.com/microsoft/iqsharp): Q# için Jupyter çekirdeği ve Python ana bilgisayar işlevinin yanı sıra bulut ortamlarında IQ# kullanmak için Docker görüntüleri.
- [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr): https://docs.microsoft.com/quantum adresinde yayımlanan belgeler için kaynak kodu.

> [!NOTE]
> Şu anda [**microsoft/Quantum-NC**](https://github.com/microsoft/Quantum-NC) deposunda ne yazık ki kod ve belge katkılarını kabul edemiyoruz ancak hata raporlarını hala memnuniyetle karşılıyoruz.

Ayrıca, farklı olaylara veya Quantum Development Kit ile ilgili yardımcı işlevlere odaklanan daha uzman birkaç depo daha mevcuttur.

- [**msr-quarc/qsharp.sty**](https://github.com/msr-quarc/qsharp.sty): Q# söz dizimi için LaTeX biçimlendirme desteği.
- [**msr-quarc/intern-workshop-2019**](https://github.com/msr-quarc/intern-workshop-2019): 2019 stajyer atölyesinde berilen Deutsch–Jozsa öğreticisi için IQ# Not Defteri.

## <a name="next-steps"></a>Sonraki adımlar ##

Quantum Development Kit topluluğunun bir parçası olduğunuz için teşekkür ederiz. Katkılarınızı heyecanla bekliyoruz!
Katkıda bulunma hakkında daha fazla bilgi edinmek istiyorsanız lütfen aşağıdaki kılavuzlardan biriyle devam edin.

> [!div class="nextstepaction"]
> [Hataları nasıl bildireceğinizi öğrenin](xref:microsoft.quantum.contributing.reporting)

> [!div class="nextstepaction"]
> [Belgelere nasıl katkıda bulunabileceğinizi öğrenin](xref:microsoft.quantum.contributing.docs)

> [!div class="nextstepaction"]
> [Çekme isteklerini nasıl açabileceğinizi öğrenin](xref:microsoft.quantum.contributing.pulls)

