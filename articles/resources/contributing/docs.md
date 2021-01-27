---
title: Microsoft QDK 'ye katkıda bulunan belgeler
description: Kavramsal veya API içeriğinin Microsoft hisse belgesi kümesine nasıl katkıda bulunabileceğinizi öğrenin.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.docs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8602705d2dd071e822e2ff58a9a44cd0684f77f1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857354"
---
# <a name="improving-documentation"></a>İyileştirme Belgeleri

Hisse geliştirme kiti için belgeler birçok farklı biçimde sürer. Bu bilgiler, bilgi almak için daha kolay kullanılabilir.

[Belgeler kodu olarak, kod olarak](https://www.writethedocs.org/guide/docs-as-code/), tüm hisse Geliştirme Seti belgeleri kod olarak biçimlendirilir ve GIT kullanarak, hisse geliştirme setini oluşturmak için kullanılan kaynak kodla aynı şekilde yönetilir.
Çoğu durumda, kod yedekleme belgelerinin çeşitli [markı](https://daringfireball.net/projects/markdown/)biçimlerinden biri, zengin biçimli bir metnin, komut satırında, Ides 'te ve kaynak denetimiyle birlikte kullanılması kolay bir düz metin biçiminde yazılmasına yönelik bir dildir.
Benzer şekilde, aşağıda açıklandığı gibi LaTeX dilini kullanarak belgelerde matematik olarak biçimlendirmeye izin vermek için [MathJax](https://www.mathjax.org/) kitaplığını benimseyin.


Bu şekilde, her belge formu ayrıntılarda biraz farklılık gösterir:

- **Kavramsal belgeler** , ' de yayımlanan bir makale https://docs.microsoft.com/quantum grubundan oluşur ve hisse kullanımı temellerini, değişim biçimleri için teknik belirtimlere göre anlatmaktadır. Bu makaleler, zengin belge kümeleri oluşturmak için kullanılan bir Markaşağı varyantı olan [Docfx-flavored markaşağı (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)dilinde yazılmıştır.
- **API başvurusu** , üzerinde yayınlanan her bir Q# işlev, işlem ve Kullanıcı tanımlı tür için bir sayfa kümesidir https://docs.microsoft.com/qsharp/api/ . Bu sayfalar, her çağrılabilir girdi ve işlemi örneklerle birlikte ve daha fazla bilgi için bağlantıları belgeleyin. API başvurusu, Q# her sürümün parçası olarak kaynak kodundaki küçük DFM belgelerinden otomatik olarak ayıklanır.
- Her örnekle birlikte bulunan **README <!----> . MD** dosyaları ve küta, bu örnek veya Kütin nasıl kullanıldığını, ne kapsadığını ve hisse geliştirme setinin geri kalanı ile ilişkisini açıklamaktadır. Bu dosyalar [GitHub flavored Markaşağı (GFM)](https://github.github.com/gfm/)kullanılarak yazılır. Bu, DFM 'in doğrudan kod depolarına belge iliştirmek için popüler bir alternatiftir.

## <a name="contributing-to-the-conceptual-documentation"></a>Kavramsal belgelere katkıda bulunma

Kavramsal veya BENIOKU belgelerine bir iyileştirmeden katkıda bulunmak için, uygun olduğu gibi, Microsoft [**docs/hisse-docs-PR**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/hisse**](https://github.com/Microsoft/Quantum)ya da [**Microsoft/niceleykatas**](https://github.com/Microsoft/QuantumKatas)üzerinde bir çekme isteğiyle başlar.
Aşağıdaki çekme istekleri hakkında daha fazla bilgi edineceksiniz, ancak şimdilik belgeleri geliştirmekte olduğu gibi göz önünde bulundurmanız gereken birkaç nokta vardır:

- Okuyucular, çok geniş bir arka plan yelpazızdaki hisse geliştirme seti belgelerine gelir. Yüksek okul öğrencilerine ait herkes, geçirmiş fakülte yeni ve heyecan verici bir şey öğrenmek isteyen herkesin, belgeleri okumaktan bir şeyi alabilmesi gerekir. Mümkün olduğunca fazla bilgi sahibi olmak için lütfen okuyucularınızın parçası hakkında kapsamlı bilgiler kullanmayın. Daha fazla bilgi için, açık ve erişilebilir açıklamalar sağlayabilmeniz veya diğer kaynakların bağlantılarını sağlayabilmeniz çok yararlı olur.
- Belge kümeleri kitap veya kağıtlar gibi düzenlenmez, bu da okuyucular "Orta" gibi görünse de ulaşacaktır. Örneğin, arama motorları Dizin önermeyebilir veya yardım almaya çalışan bir arkadaşınız tarafından bir bağlantı göndermiş olabilirler. Uygun yerlerde olan bağlantılarla birlikte her zaman açık bir bağlam sunarak okuyucunuzun yardımına yardımcı olmaya çalışın.
- Bazı okuyucular Özet deyimler ve tanımları en yararlı bulurken, diğer okuyucular somut örneklerden yararlanarak en iyi şekilde çalışır. Hem genel durumun hem de belirli örneklerin sağlanması, her iki okuyucunun de en fazla hisse programlamayla programlama sağlanmasına yardımcı olabilir.
- Özellikle de belgelenmekte olan kodu de yazmış olmanız durumunda, okuyucunuz için hiç açık olmayan bir şey sizin için açık olabilir. Programınızın en iyi bir en iyi yolu yoktur; bu nedenle, bir okuyucunun ne kadar süden olduğunu veya öğrendiğine bakılmaksızın, fikirlerinizi kodda ifade etmek için en yararlı bulduğunuz tasarım modellerini tahmin edemeyebilir. Bir okuyucunun kodunuzun kullanımını nasıl beklediğini öğrenmek, bu bağlamın sağlanmasına yardımcı olabilir.
- Hisse programlama topluluğunun birçok üyesi akademik araştırmacılar ve temel olarak topluluk katkılarına yönelik alıntılar aracılığıyla tanınır. Okuyucuların ek malzemeler bulmasına yardımcı olmaya ek olarak, incelemeler, Talks, blog gönderileri ve yazılım araçları gibi akademik çıkışları doğru bir şekilde ayırarak, akademik katkıların topluluğu geliştirmek için en iyi işleri yapmasına yardımcı olabilir.
- Hisse programlama topluluğu, geniş ve wonderfully farklı bir topluluktur. Üçüncü kişi örneklerinde genimli zamirler kullanımı (örn................................... Kişilerin alıntılar ve bağlantılarla ilgili adlarını bilmekte ve ASCII olmayan karakterlerin doğru eklenmesi, üyelerinin üyelerine göre, topluluk çeşitliliğine hizmet verebilir. Benzer şekilde, Ingilizce dilde pek çok sözcük genellikle bir şekilde kullanılır. bu şekilde, teknik belgelerde kullanımları hem bireysel okuyucular hem de topluluk için büyük ölçekli bir zarar oluşmasına neden olabilir.

### <a name="referencing-sample-code-from-conceptual-articles"></a>Kavramsal makalelerden örnek koda başvurma

[Örnek deposundan](https://github.com/Microsoft/Quantum)kod eklemek istiyorsanız, özel bir DocFX-Flavored Marku komutu kullanarak bunu yapabilirsiniz:

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

Bu komut, [ `Game.qs` dosyadaki `chsh-game` ](https://github.com/microsoft/Quantum/blob/main/samples/algorithms/chsh-game/Game.qs)4 ' e kadar olan satırları, Q# söz dizimi vurgulamanın amacı için kod olarak işaretleyerek, örnekten içeri aktarır.
Bu komutu kullanarak, kavramsal makaleler ve örnekler deposu arasında kodu çoğaltmaktan kaçınabilirsiniz. böylece, belgelerde örnek kod her zaman mümkün olduğunca güncel olur.

### <a name="contributing-image-files"></a>Katkıda bulunan görüntü dosyaları

**Önemli**: görüntülerin koyu modda düzgün bir şekilde işlemesini sağlamak için saydamlıkları kullanmaktan kaçınmalısınız.

- . Jpg dosyaları için. . jpg biçimi saydam öğeleri desteklemediğinden hiçbir şey yapmanız gerekmez.
- . Png dosyaları için, bir beyaz arka plan eklemeniz veya Alfa kanalının değerini **100** olarak değiştirmeniz gerekir. Bunu Windows 'da yapmanın en kolay yolu, **Paint** 'te dosyayı açmak ve özgün dosyanın üzerine yazarak dosyayı kaydetmek için kullanılır.
- . SVG dosyaları için en düşük katmana beyaz dikdörtgen eklemeniz gerekir. Bunu **Inkscape** ile yapabilirsiniz:
  1. . SVG dosyasını açın.
  1. Kare Oluşturucu aracını seçin ve orijinal şeklin üzerine bir beyaz dikdörtgen çizin.
  1. Koyu oka tıklayarak veya **F1** tuşuna basarak **nesneleri seçin ve dönüştürün '** ı seçin.
  1. Dikdörtgenin seçili olmasına karşın, alt araç öğesini alt kısımdaki **Seçime (End)** tıklayın.
  1. Dikdörtgeni farenizle veya ok tuşlarıyla ayarlayın.

## <a name="contributing-to-the-api-references"></a>API başvurularına katkıda bulunma

API başvurularına bir iyileştirmeden katkıda bulunmak için, bir çekme isteğini doğrudan belgelenmiş kodda açmak çok faydalı olur.
Her işlev, işlem veya Kullanıcı tanımlı tür bir belge açıklamasını destekler (yerine ile gösterilir `///` `//` ).
Hisse geliştirme setinin her bir sürümünü derliyoruz. bu yorumlar, https://docs.microsoft.com/qsharp/api/ her çağrılabilir giriş ve çıkışları, her çağrılabilir şekilde yaptığı varsayımlar ve bunların nasıl kullanılacağına ilişkin ayrıntılar dahil olmak üzere ' de API başvurusunu oluşturmak için kullanılır.

> [!IMPORTANT]
> Lütfen oluşturulan API belgelerini el ile düzenlemediğinizden emin olun. Bu dosyalar her yeni sürümde üzerine yazılır.
> Topluluğa katkılarınız için değer veriyoruz ve kullanıcıların sürümden sonra serbest olmasına yardımcı olmaya devam etmesini sağlamak istiyorsunuz.

Örneğin, işlevini düşünün `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)` .
Bir belge yorumu, bir kullanıcının nasıl yorumlayacağını `bits` ve işlevin ne olduğunu öğreni konusunda bilgi edinmelidir `oracle` .
Bu farklı bilgi parçalarının her biri, Q# belge açıklamasında özel olarak adlandırılmış bir Markaşağı bölümü tarafından derleyiciye alınabilir.
Örneği için aşağıdakine `ControlledOnBitString` benzer bir şey yazabiliriz:

```qsharp
 /// # Summary
 /// Returns a unitary operation that applies an oracle on the target register if the 
 /// control register state corresponds to a specified bit mask.
 ///
 /// # Description
 /// The output of this function is an operation that can be represented by a
 /// unitary transformation $U$ such that
 /// \begin{align}
 ///     U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes
 ///     \begin{cases}
 ///         V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\
 ///         \ket{\psi} & \textrm{otherwise}
 ///     \end{cases},
 /// \end{align}
 /// where $V$ is a unitary transformation that represents the action of the
 /// `oracle` operation.
 ///
 /// # Input
 /// ## bits
 /// The bit string to control the given unitary operation on.
 /// ## oracle
 /// The unitary operation to be applied on the target register.
 ///
 /// # Output
 /// A unitary operation that applies `oracle` on the target register if the control 
 /// register state corresponds to the bit mask `bits`.
 ///
 /// # Remarks
 /// The length of `bits` and `controlRegister` must be equal.
 ///
 /// Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function
 /// is an operation that performs the following steps:
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits`;
 /// * apply `Controlled oracle` to the control and target registers;
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits` again to return the control register to the original state.
 ///
 /// The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.
 ///
 /// # Example
 /// The following code snippets are equivalent:
 /// ```qsharp
 /// (ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
 /// ```
 /// and
 /// ```qsharp
 /// within {
 ///     ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
 /// } apply {
 ///     Controlled oracle(controlRegister, targetRegister);
 /// }
 /// ```
 ///
 /// The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:
 /// ```qsharp
 /// using (register = Qubit[2]) {
 ///     ApplyToEach(H, register);
 ///     (ControlledOnBitString([false], Z))(register[0..0], register[1]);
 /// }
 /// ```
 function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
 {
     return ControlledOnBitStringImpl(bits, oracle, _, _);
 }
```

Yukarıdaki kodun işlenmiş sürümünü, [ `ControlledOnBitString` işlevin API belgelerinde](xref:Microsoft.Quantum.Canon.ControlledOnBitString)görebilirsiniz.

Belge yazma hakkında genel olarak, API belge açıklamalarını yazma bölümünde birkaç şeyi aklınızda tutmaya yardımcı olur:

- Her belge açıklamasının biçimi, Q# derleyicinin belgelerinize doğru görünmesini beklediklerini eşleştirmek için sahiptir. `/// # Remarks`Bölüm gibi bölümler daha kısıtlayıcı olsa da, serbest biçimli içeriğe izin ver gibi bazı bölümler `/// # See Also` .
- Bir okuyucu, API belgelerinizi ana API başvuru sitesinde, her bir ad alanının özetinde veya hatta, üzerine gelme bilgilerini kullanarak IDE içinden okuyabilir. `/// # Summary`Bunun yaklaşık bir cümle olduğundan emin olmak, okuyucunun daha fazla okuma yapmak veya başka bir yere bakmak gerekip gerekmediğini hızlı bir şekilde izlemesine yardımcı olur ve ad alanı özetleri aracılığıyla hızla tarama yapmaya yardımcı olabilir.
- Belgeleriniz kodun kendisinden çok daha uzun bir süre daha fazla olabilir, ancak bu tamam! Küçük bir kod parçası bile, bu kodun bulunduğu bağlamı bilmiyor olan kullanıcılar için beklenmeyen etkileri olabilir. Somut örnekler ve açık açıklamalar sunarak kullanıcıların, kendileri için kullanılabilir olan kodun en iyi şekilde kullanılmasını sağlayabilirsiniz.

<!-- ## LaTeX Formatting ##

**TODO** -->
