---
title: Microsoft QDK 'ye katkıda bulunan kod
description: Örnek ve kitaplık kodunun Microsoft Quantum Development Kit (QDK) ile nasıl katkıda bulunabileceğinizi öğrenin.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
no-loc:
- Q#
- $$v
ms.openlocfilehash: 7a258a915a807b8e1ee7c2c9c062017d90f6a454
ms.sourcegitcommit: 685a8ab16d7e6a25e63a168d6e7c385fa6e876cc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91489774"
---
# <a name="contributing-code"></a>Koda Katkıda Bulunma

Sorunları raporlamaya ve belgelerin geliştirilmesine ek olarak, hisse geliştirme seti 'ne katkıda bulunan kod, hisse programlama topluluğundaki eşlere yardımcı olmanın çok doğrudan bir yolu olabilir.
Kod katkısından, sorunları gidermeye, yeni örnekler sağlamanıza, var olan kitaplıkların kullanımını daha kolay hale getirmenize veya hatta tamamen yeni özellikler eklemenize yardımcı olabilirsiniz.

Bu kılavuzda, katkıınızın en iyi şekilde faydalanmaya yardımcı olmak için çekme isteklerini gözden geçirdiğimiz sırada baktığımız bir şeyi ayrıntılandırıyoruz.

## <a name="what-we-look-for"></a>Şuna baktık

İdeal bir kod katkısı, sorunları gidermek, mevcut özellikleri genişletmek veya bir deponun kapsamı içinde olan yeni özellikler eklemek için bir hisse geliştirme seti deposundaki mevcut çalışmayı oluşturur.
Bir kod katkısı kabul ettiğimiz zaman, bu, hisse geliştirme setinin bir parçası haline gelir. bu şekilde, yeni özellikler ücretlendirilecektir, tutulur ve, hisse geliştirme setinin geri kalanı ile aynı şekilde geliştirilir.
Bu nedenle, bir katkı tarafından eklenen işlevlerin iyi test edildiğini ve belgelendirildiğine yardımcı olur.

### <a name="unit-tests"></a>Birim testleri

Q#Canon gibi kitaplıkları oluşturan işlevler, işlemler ve Kullanıcı tanımlı türler, [**Microsoft/Histumlibraries**](https://github.com/Microsoft/QuantumLibraries/) deposunda geliştirmenin bir parçası olarak otomatik olarak test edilir.
Örneğin, yeni bir çekme isteği açıldığında, [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) yapılandırmanızla, çekme isteğindeki değişikliklerin, hisse programlama topluluğunun bağlı olduğu mevcut işlevleri bozmadığını kontrol eder.

En son Q# sürümde, birim testleri özniteliği kullanılarak tanımlanır `@Test("QuantumSimulator")` . Bağımsız değişken, "Histumsimülatör", "Toffzeytin", "Tracesimülatör" veya Run hedefini belirten tam nitelikli bir ad olabilir. Farklı çalışma hedeflerini tanımlayan birkaç öznitelik aynı çağrılabilir öğesine iliştirilebilir. Bazı testlerimizde, xUnit çerçevesine biten tüm işlevleri ve işlemleri sunan kullanım dışı [Microsoft. hisse. xUnit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) paketini kullanmaya devam edersiniz Q# `Test` . [xUnit](https://xunit.github.io/) Bu paket artık birim testlerini tanımlamak için gerekli değildir. 

Aşağıdaki işlev, <xref:microsoft.quantum.canon.fst> ve <xref:microsoft.quantum.canon.snd> işlevlerinin her ikisinin de bir temsilci örneğinde doğru çıkışları döndürmesini sağlamak için kullanılır.
`Fst`Veya çıkışı `Snd` yanlışsa, `fail` test başarısız olmasına neden olması için ifade kullanılır.

```qsharp
@Test("QuantumSimulator")
function PairTest () : Unit {
    let pair = (12, PauliZ);

    if (Fst(pair) != 12) {
        let actual = Fst(pair);
        fail $"Expected 12, actual {actual}.";
    }

    if (Snd(pair) != PauliZ) {
        let actual = Snd(pair);
        fail $"Expected PauliZ, actual {actual}.";
    }
}
```

Standart kitaplıklar kılavuzunun [Test bölümündeki](xref:microsoft.quantum.libraries.diagnostics) teknikler kullanılarak daha karmaşık koşullar denetlenebilir.
Örneğin, aşağıdaki test `H(q); X(q); H(q);` tarafından çağrılışını <xref:microsoft.quantum.canon.applywith> , ile aynı şeyi yapar `Z(q)` .

```Q#
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

Yeni özellikler eklerken, katkınızın beklenen şeyi kullandığından emin olmak için yeni testler de eklemek iyi bir fikirdir.
Bu, topluluğun geri kalanında özelliği bakımını ve geliştirmeyi sağlar ve özellikle de diğer geliştiricilerin özelliğinizin güvenebileceklerini bilmesini sağlar.

> [!NOTE]
> Bu, etrafında çok farklı bir şekilde çalışmaktadır!
> Bazı testleri eksik olan bir özellik varsa, test kapsamı ekleyememize yardımcı olmak topluluğa harika bir katkı sağlar.

Yerel olarak, `dotnet test` bir çekme isteği açmadan önce katkılarınızı kontrol edebilmeniz Için Visual Studio Test Gezgini veya komutu kullanılarak birim testleri çalıştırılabilir.

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="pull-requests"></a>Çekme İstekleri

Çalışmanızı katkıda bulunmak için hazırsanız lütfen ilgili depoya GitHub aracılığıyla bir çekme Isteği gönderin.
Takım gözden geçirir ve geri bildirim sağlar. Tüm yorumların yanıtlanması ve çözümlenmesi gerekir ve kod Dalla birleştirilmeden önce tüm denetimlerin geçmesi gerekir `main` .

## <a name="when-well-reject-a-pull-request"></a>Çekme Isteğini reddedeceğiz

Bazen bir katkı için çekme isteğini reddedeceğiz.
Bu sizin için söz konusu olduğunda, belirli bir katkıyı kabul edemediğimiz bir kaç nedenden dolayı bu durum kötü olduğu anlamına gelmez.
En yaygın olarak, hisse programlama topluluğu için bir katkı gerçekten iyi bir yoldur, ancak hisse geliştirme seti depoları bu uygulamayı geliştirmek için doğru yerde değildir.
Bu gibi durumlarda, her ne kadar kendi deponuzu, hisse geliştirme setinin kuvvetinin bir parçası olan---, GitHub ve NuGet.org kullanarak kendi kitaplıklarınızı kolayca oluşturmanın ve dağıtmanın yanı sıra Canon ve kimya kitaplıklarını dağıtdığımız şekilde sizin de kolayca dağıtmanızı öneririz.

Diğer zamanlarda, henüz bakımını yapmaya ve geliştirmeye hazır olmadığınızdan, iyi bir katkıyı reddedebiliriz.
Her şeyi yapmak zor olabilir. bu nedenle, bir yol haritası olarak hangi özelliklerin en iyi şekilde çalışabileceklerini planlıyoruz.
Bu, bir özelliğin üçüncü taraf bir kitaplık olarak bırakılması çok daha anlamlı hale geçirebileceği bir durum olabilir.
Alternatif olarak, bununla ilgili en iyi işi yapabilmemiz için bir özelliği, yol etiketimize daha iyi uyum sağlayacak şekilde değiştirme konusunda yardım almak için sorun yaşayabilirsiniz.

Ayrıca, bunu kullanmamıza yardımcı olması için daha fazla belge veya birim testi gerektiriyorsa veya Q# kullanıcıların özelliğinizi bulmasını zortacağından, kitaplıkların geri kalanından yeterince farklıysa bir çekme isteğinde değişiklik yapmanızı isteyeceğiz.
Bu durumlarda, katkılarınızın dahil etmemizi kolaylaştırmak için nelerin eklenebileceği veya değiştirilebilecek hakkında kod incelemelerinde bazı tavsiyeler sunmaya çalışacaktır.

Son olarak, [Microsoft açık kaynak kullanım kuralları](https://opensource.microsoft.com/codeofconduct/)' nda açıklandığı gibi hisse bilgi işlem Topluluğu ' na zarar veren katkılarını kabul edemedik.
Katkıların tüm hisse bilgi işlem topluluğuna, hem geçerli harika çeşitliliğe hem de daha da fazla bir şekilde büyümeye devam ettiğinden emin olmak istiyoruz.
Bu hedefi gerçekleştirme konusunda yardımımız olduğunu biliyoruz.

## <a name="next-steps"></a>Sonraki adımlar

Hisse geliştirme setini tüm hisse programlama topluluğu için harika bir kaynak haline getirmek için teşekkürler!
Daha fazla bilgi edinmek için lütfen stil sayfasında aşağıdaki kılavuzla devam edin Q# .

> [!div class="nextstepaction"]
> [Stil yönergeleri hakkında bilgi edinin Q#](xref:microsoft.quantum.contributing.style)

Katkıda bulunduğunuz kod türüne bağlı olarak, katkılarınızı mümkün olduğunca çok iyi hale getirmenize yardımcı olabilecek başka şeyler de olabilir.

> [!div class="nextstepaction"]
> [Katkıda bulunan örnekler hakkında bilgi edinin](xref:microsoft.quantum.contributing.samples)
