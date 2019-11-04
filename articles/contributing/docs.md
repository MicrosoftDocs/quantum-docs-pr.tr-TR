---
title: Katkıda bulunan belgeler | Microsoft Docs
description: Katkıda bulunan belgeler
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
ms.openlocfilehash: 1e24dd859c0b75a161f4f3c7151e2eec227075a2
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183684"
---
# <a name="improving-documentation"></a>Belgeleri geliştirme #

Hisse geliştirme kiti için belgeler birçok farklı biçimde sürer. Bu bilgiler, bilgi almak için daha kolay kullanılabilir.

[Belgeler kodu olarak, kod olarak](https://www.writethedocs.org/guide/docs-as-code/), tüm hisse Geliştirme Seti belgeleri kod olarak biçimlendirilir ve GIT kullanarak, hisse geliştirme setini oluşturmak için kullanılan kaynak kodla aynı şekilde yönetilir.
Çoğu durumda, kod yedekleme belgelerinin çeşitli [markı](https://daringfireball.net/projects/markdown/)biçimlerinden biri, zengin biçimli bir metnin, komut satırında, Ides 'te ve kaynak denetimiyle birlikte kullanılması kolay bir düz metin biçiminde yazılmasına yönelik bir dildir.
Benzer şekilde, aşağıda açıklandığı gibi LaTeX dilini kullanarak belgelerde matematik olarak biçimlendirmeye izin vermek için [MathJax](https://www.mathjax.org/) kitaplığını benimseyin.


Bu şekilde, her belge formu ayrıntılarda biraz farklılık gösterir:

- **Kavramsal belgeler** https://docs.microsoft.com/quantum yayımlanan bir makale grubundan oluşur ve hisse bilgi işlem esaslarından değişim biçimleri için teknik belirtimlere kadar her şeyi anlatmaktadır. Bu makaleler, zengin belge kümeleri oluşturmak için kullanılan bir Markaşağı varyantı olan [Docfx-flavored markaşağı (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)dilinde yazılmıştır.
- **API başvurusu** , https://docs.microsoft.com/qsharp/api/ yayımlanan her Q # işlevi, işlem ve Kullanıcı tanımlı tür için bir sayfa kümesidir. Bu sayfalar, her çağrılabilir girdi ve işlemi örneklerle birlikte ve daha fazla bilgi için bağlantıları belgeleyin. API başvurusu, her yayının bir parçası olarak Q # kaynak kodundaki küçük DFM belgelerinden otomatik olarak ayıklanır.
- Her örnekle birlikte bulunan **README<!---->. MD** dosyaları ve küta, bu örnek veya Kütin nasıl kullanıldığını, ne kapsadığını ve bu dosyanın hisse geliştirme setinin geri kalanı ile ilişkisini açıklamaktadır. Bu dosyalar [GitHub flavored Markaşağı (GFM)](https://github.github.com/gfm/)kullanılarak yazılır. Bu, DFM 'in doğrudan kod depolarına belge iliştirmek için popüler bir alternatiftir.

## <a name="contributing-to-the-conceptual-documentation"></a>Kavramsal belgelere katkıda bulunma ##

Kavramsal veya BENIOKU belgelerine bir iyileştirmeden katkıda bulunmak için, uygun olduğu gibi, Microsoft [**docs/hisse-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/hisse**](https://github.com/Microsoft/Quantum)ya da [**Microsoft/niceleykatas**](https://github.com/Microsoft/QuantumKatas)üzerinde bir çekme isteğiyle başlar.
Aşağıdaki çekme istekleri hakkında daha fazla bilgi edineceksiniz, ancak şimdilik belgeleri geliştirmekte olduğu gibi göz önünde bulundurmanız gereken birkaç nokta vardır:

- Okuyucular, çok geniş bir arka plan yelpazızdaki hisse geliştirme seti belgelerine gelir. Yüksek okul öğrencilerine ait herkes, geçirmiş fakülte yeni ve heyecan verici bir şey öğrenmek isteyen herkesin, belgeleri okumaktan bir şeyi alabilmesi gerekir. Mümkün olduğunca fazla bilgi sahibi olmak için lütfen okuyucularınızın parçası hakkında kapsamlı bilgiler kullanmayın. Daha fazla bilgi için, açık ve erişilebilir açıklamalar sağlayabilmeniz veya diğer kaynakların bağlantılarını sağlayabilmeniz çok yararlı olur.
- Belge kümeleri kitap veya kağıtlar gibi düzenlenmez, bu da okuyucular "Orta" gibi görünse de ulaşacaktır. Örneğin, arama motorları Dizin önermeyebilir veya yardım almaya çalışan bir arkadaşınız tarafından bir bağlantı göndermiş olabilirler. Uygun yerlerde olan bağlantılarla birlikte her zaman açık bir bağlam sunarak okuyucunuzun yardımına yardımcı olmaya çalışın.
- Bazı okuyucular Özet deyimler ve tanımları en yararlı bulurken, diğer okuyucular somut örneklerden yararlanarak en iyi şekilde çalışır. Hem genel durumun hem de belirli örneklerin sağlanması, her iki okuyucunun de en fazla hisse programlamayla programlama sağlanmasına yardımcı olabilir.
- Özellikle de belgelenmekte olan kodu de yazmış olmanız durumunda, okuyucunuz için hiç açık olmayan bir şey sizin için açık olabilir. Programınızın en iyi bir en iyi yolu yoktur; bu nedenle, bir okuyucunun ne kadar süden olduğunu veya öğrendiğine bakılmaksızın, fikirlerinizi kodda ifade etmek için en yararlı bulduğunuz tasarım modellerini tahmin edemeyebilir. Bir okuyucunun kodunuzun kullanımını nasıl beklediğini öğrenmek, bu bağlamın sağlanmasına yardımcı olabilir.
- Hisse programlama topluluğunun birçok üyesi akademik araştırmacılar ve temel olarak topluluk katkılarına yönelik alıntılar aracılığıyla tanınır. Okuyucuların ek malzemeler bulmasına yardımcı olmaya ek olarak, incelemeler, Talks, blog gönderileri ve yazılım araçları gibi akademik çıkışları doğru bir şekilde ayırarak, akademik katkıların topluluğu geliştirmek için en iyi işleri yapmasına yardımcı olabilir.
- Hisse programlama topluluğu, geniş ve wonderfully farklı bir topluluktur. Üçüncü kişi örneklerinde genimli zamirler kullanımı (örn................................... Kişilerin alıntılar ve bağlantılarla ilgili adlarını bilmekte ve ASCII olmayan karakterlerin doğru eklenmesi, üyelerinin üyelerine göre, topluluk çeşitliliğine hizmet verebilir. Benzer şekilde, Ingilizce dilde pek çok sözcük genellikle bir şekilde kullanılır. bu şekilde, teknik belgelerde kullanımları hem bireysel okuyucular hem de topluluk için büyük ölçekli bir zarar oluşmasına neden olabilir.

## <a name="contributing-to-the-api-references"></a>API başvurularına katkıda bulunma ##

API başvurularına bir iyileştirmeden katkıda bulunmak için, bir çekme isteğini doğrudan belgelenmiş kodda açmak çok faydalı olur.
Her işlev, işlem veya Kullanıcı tanımlı tür bir belge açıklamasını destekler (`//`yerine `///` gösterilir).
Her bir bilgi işlem geliştirme setinin her sürümünü derliyoruz, bu yorumlar, her çağrılabilir giriş ve çıkışları, her çağrılabilir şekilde yaptığı varsayımlar ve bunların nasıl kullanılacağına ilişkin ayrıntılar dahil olmak üzere https://docs.microsoft.com/qsharp/api/ ' de API başvurusunu oluşturmak için kullanılır.

> [!IMPORTANT]
> Lütfen oluşturulan API belgelerini el ile düzenlemediğinizden emin olun. Bu dosyalar her yeni sürümde üzerine yazılır.
> Topluluğa katkılarınız için değer veriyoruz ve kullanıcıların sürümden sonra serbest olmasına yardımcı olmaya devam etmesini sağlamak istiyorsunuz.

Örneğin, `PrepareTrialState(angles : Double[], register : Qubit[]) : Unit`bir işlem düşünün.
Bir belge yorumu, bir kullanıcının `angles`nasıl yorumlayacağını, `register`başlangıç durumu hakkında ne olduğunu, `register` ne tür etkileri olduğunu ve bu şekilde olduğunu öğrenmelidir.
Bu farklı bilgi parçalarının her biri, belge açıklamasında özel olarak adlandırılmış bir Markaşağı bölümü tarafından Q # derleyicisine temin edilebilir.
`PrepareTrialState`örneği için aşağıdakine benzer bir şey yazabiliriz:

```qsharp
/// # Summary
/// Given a register of qubits, prepares them in a trial state by rotating each
/// independently.
///
/// # Description
/// This operation prepares the input register by performing a
/// $Y$ rotation on each qubit by an angle given in `angles`.
///
/// # Input
/// ## angles
/// An array of parameters
/// ## register
/// A register of qubits initially in the $\ket{00\cdots0}$ state.
///
/// # Example
/// To prepare an equal superposition $\ket{++\cdots+}$ over all input qubits:
/// ```qsharp
/// PrepareTrialState(ConstantArray(Length(register), PI() / 2.0), register);
/// ```
///
/// # Remarks
/// This operation is generally useful in the inner loop of an optimization
/// algorithm.
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.Ry
operation PrepareTrialState(angles : Double[], register : Qubit[]) : Unit {
    // ...
}
```

Belge yazma hakkında genel olarak, API belge açıklamalarını yazma bölümünde birkaç şeyi aklınızda tutmaya yardımcı olur:

- Her belge açıklamasının biçimi, Q # derleyicisinin belgelerinize doğru görünmesini beklediklerini eşleşmelidir. `/// # Remarks` serbest biçim içeriğine izin vermek gibi bazı bölümler, `/// # See Also` bölümü gibi bölümler daha kısıtlayıcı.
- Bir okuyucu, API belgelerinizi ana API başvuru sitesinde, her bir ad alanının özetinde veya hatta, üzerine gelme bilgilerini kullanarak IDE içinden okuyabilir. `/// # Summary` cümleden daha uzun olmadığından emin olmak, okuyucunun daha fazla okuma yapmak veya başka bir yere bakmak gerekip gerekmediğini hızlı bir şekilde sıralamasına yardımcı olur ve ad alanı özetleri aracılığıyla hızla tarama yapmaya yardımcı olabilir.
- Belgeleriniz kodun kendisinden çok daha uzun bir süre daha fazla olabilir, ancak bu tamam! Küçük bir kod parçası bile, bu kodun bulunduğu bağlamı bilmiyor olan kullanıcılar için beklenmeyen etkileri olabilir. Somut örnekler ve açık açıklamalar sunarak kullanıcıların, kendileri için kullanılabilir olan kodun en iyi şekilde kullanılmasını sağlayabilirsiniz.

<!-- ## LaTeX Formatting ##

**TODO** -->
