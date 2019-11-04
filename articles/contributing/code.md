---
title: Katkıda bulunan kod | Microsoft Docs
description: Katkıda bulunan kod
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: cca50e6c63d4bb982aa5f0a59fc19d08ecbec508
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185911"
---
# <a name="contributing-code"></a>Katkıda bulunan kod #

Sorunları raporlamaya ve belgelerin geliştirilmesine ek olarak, hisse geliştirme seti 'ne katkıda bulunan kod, hisse programlama topluluğundaki eşlere yardımcı olmanın çok doğrudan bir yolu olabilir.
Kod katkısından, sorunları gidermeye, yeni örnekler sağlamanıza, var olan kitaplıkların kullanımını daha kolay hale getirmenize veya hatta tamamen yeni özellikler eklemenize yardımcı olabilirsiniz.

Bu kılavuzda, katkıınızın en iyi şekilde faydalanmaya yardımcı olmak için çekme isteklerini gözden geçirdiğimiz sırada baktığımız bir şeyi ayrıntılandırıyoruz.

## <a name="what-we-look-for"></a>Şuna baktık ##

İdeal bir kod katkısı, sorunları gidermek, mevcut özellikleri genişletmek veya bir deponun kapsamı içinde olan yeni özellikler eklemek için bir hisse geliştirme seti deposundaki mevcut çalışmayı oluşturur.
Bir kod katkısı kabul ettiğimiz zaman, bu, hisse geliştirme setinin bir parçası haline gelir. bu şekilde, yeni özellikler ücretlendirilecektir, tutulur ve, hisse geliştirme setinin geri kalanı ile aynı şekilde geliştirilir.
Bu nedenle, bir katkı tarafından eklenen işlevlerin iyi test edildiğini ve belgelendirildiğine yardımcı olur.

### <a name="unit-tests"></a>Birim testleri ###

Canon gibi kitaplıkları oluşturan Q # işlevleri, işlemler ve Kullanıcı tanımlı türler, [**Microsoft/Histumlibraries**](https://github.com/Microsoft/QuantumLibraries/) deposunda geliştirmenin bir parçası olarak otomatik olarak test edilir.
Örneğin, yeni bir çekme isteği açıldığında, [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) yapılandırmanızla, çekme isteğindeki değişikliklerin, hisse programlama topluluğunun bağlı olduğu mevcut işlevleri bozmadığını kontrol eder.
Bu sınamalar, [xUnit](https://xunit.github.io/) çerçevesi için test olarak Q # işlevlerini ve işlemlerini kullanıma sunan [Microsoft. hisse. xUnit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) paketi kullanılarak yazılır.

[`Standard/tests/Standard.Tests.csproj`](https://github.com/microsoft/QuantumLibraries/blob/master/Standard/tests/Standard.Tests.csproj) , `Test`biten işlevleri veya işlemleri çalıştırmak Için bu xUnit tümleştirmesini kullanır.
Örneğin, <xref:microsoft.quantum.canon.fst> ve <xref:microsoft.quantum.canon.snd> işlevlerinin hem temsilci bir örnekteki doğru çıkışları döndürmesini sağlamak için aşağıdaki işlev kullanılır.
`Fst` veya `Snd` çıkışı yanlışsa, testin başarısız olmasına neden olması için `fail` deyimleri kullanılır.

```qsharp
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
Örneğin, aşağıdaki test, <xref:microsoft.quantum.canon.applywith> tarafından çağrılan `H(q); X(q); H(q);` `Z(q)`ile aynı şeyi yapar.

```qsharp
operation WithTest () : Unit {
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

Yerel olarak, bir çekme isteğini açmadan önce katkılarınızı kontrol edebilmeniz için Visual Studio Test Gezgini veya `dotnet test` komutu kullanılarak birim testleri çalıştırılabilir.

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="when-well-reject-a-pull-request"></a>Çekme Isteğini reddedeceğiz ##

Bazen bir katkı için çekme isteğini reddedeceğiz.
Bu sizin için söz konusu olduğunda, belirli bir katkıyı kabul edemediğimiz bir kaç nedenden dolayı bu durum kötü olduğu anlamına gelmez.
En yaygın olarak, hisse programlama topluluğu için bir katkı gerçekten iyi bir yoldur, ancak hisse geliştirme seti depoları bu uygulamayı geliştirmek için doğru yerde değildir.
Bu gibi durumlarda, her ne kadar kendi deponuzu, hisse geliştirme setinin kuvvetinin bir parçası olan---,, Canon ve kimya 'yi dağıtdığımız şekilde GitHub ve NuGet.org kullanarak kendi kitaplıklarınızı oluşturmanın ve dağıtmanın kolay bir yolu olmasını kesinlikle öneririz. kitaplıkları bugün.

Diğer zamanlarda, henüz bakımını yapmaya ve geliştirmeye hazır olmadığınızdan, iyi bir katkıyı reddedebiliriz.
Her şeyi yapmak zor olabilir. bu nedenle, bir yol haritası olarak hangi özelliklerin en iyi şekilde çalışabileceklerini planlıyoruz.
Bu, bir özelliğin üçüncü taraf bir kitaplık olarak bırakılması çok daha anlamlı hale geçirebileceği bir durum olabilir.
Alternatif olarak, bununla ilgili en iyi işi yapabilmemiz için bir özelliği, yol etiketimize daha iyi uyum sağlayacak şekilde değiştirme konusunda yardım almak için sorun yaşayabilirsiniz.

Ayrıca, bunu kullanmamıza yardımcı olmak üzere daha fazla belge veya birim testi gerektiriyorsa veya bir çekme isteğinde, kullanıcıların özelliğinizi bulmasını zortacağından, daha fazla bilgi almak için bir çekme isteğinde de değişiklik yapmanızı isteyeceğiz.
Bu durumlarda, katkılarınızın dahil etmemizi kolaylaştırmak için nelerin eklenebileceği veya değiştirilebilecek hakkında kod incelemelerinde bazı tavsiyeler sunmaya çalışacaktır.

Son olarak, [Microsoft açık kaynak kullanım kuralları](https://opensource.microsoft.com/codeofconduct/)' nda açıklandığı gibi hisse bilgi işlem Topluluğu ' na zarar veren katkılarını kabul edemedik.
Katkıların tüm hisse bilgi işlem topluluğuna, hem geçerli harika çeşitliliğe hem de daha da fazla bir şekilde büyümeye devam ettiğinden emin olmak istiyoruz.
Bu hedefi gerçekleştirme konusunda yardımımız olduğunu biliyoruz.

## <a name="next-steps"></a>Sonraki adımlar ##

Hisse geliştirme setini tüm hisse programlama topluluğu için harika bir kaynak haline getirmek için teşekkürler!
Daha fazla bilgi edinmek için lütfen Q # stilinde aşağıdaki kılavuzla devam edin.

> [!div class="nextstepaction"]
> [Q # stil yönergeleri hakkında bilgi edinin](xref:microsoft.quantum.contributing.style)
