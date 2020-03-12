---
title: Microsoft QDK 'ye katkıda bulunan örnekler
description: Örnek kodun Microsoft Quantum Development Kit nasıl katkıda bulunabileceğinizi öğrenin (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
ms.openlocfilehash: 3bd0de04a448c74eea6c3e8e3a15dcbb19f9d705
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024160"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a>Hisse geliştirme paketine katkıda bulunan örnekler

[Örnek deposuna](https://github.com/Microsoft/Quantum)kod katkıda bulunmak istiyorsanız, hisse geliştirme topluluğunun daha iyi bir yerde olmasını istediğiniz için teşekkürler!

## <a name="the-quantum-development-kit-samples-repository"></a>Hisse geliştirme seti örnekleri deposu

Katkılarınızı mümkün olduğunca hızlı bir şekilde hazırlamanıza yardımcı olmak için, örnek deposunun nasıl düzenlendiği hakkında hızlı bir bakış yapmanız yararlı olur:

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

Diğer bir deyişle, [Microsoft/hisse deposundaki](https://github.com/microsoft/Quantum) örnekler, `algorithms/`, `arithmetic/`veya `characterization/`gibi farklı klasörlere konu alanı tarafından ayrılır.
Her bir konu alanının klasörü içinde her örnek, bir kullanıcının bu örneği araştırmasını ve kullanması gereken her şeyi toplayan tek bir klasörden oluşur.

## <a name="how-samples-are-structured"></a>Örnekler nasıl yapılandırılır?

Her bir klasörü oluşturan dosyalara bakarak [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) örneğine göz atalım.

| Dosya              | Açıklama                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | .NET Core SDK örneği oluşturmak için kullanılan Q # projesi |
| `Game.qs`         | Q # işlem ve örnek için işlevler                 |
| `Host.cs`         | C#örneği çalıştırmak için kullanılan ana bilgisayar programı                     |
| `host.py`         | Örneği çalıştırmak için kullanılan Python konak programı                 |
| `README.md`       | Örneğin ne yaptığını ve nasıl kullanılacağını gösteren belgeler    |

Örneklerin hepsi aynı dosya kümesine sahip olmaz (örneğin, bazı örnekler C#salt olabilir, diğerlerinin bir Python ana bilgisayarı olmayabilir veya bazı örnekler, çalışma verileri dosyalarının çalışmasını gerektirebilir).

## <a name="anatomy-of-a-helpful-readme-file"></a>Faydalı bir BENIOKU dosyasının anatomumu

Yalnızca önemli bir dosya olan `README.md` dosyası, kullanıcıların örneğinizi kullanmaya başlamak için ihtiyaç duyduğu bir dosyadır!

Her `README.md` katkılarınızı bulmaya docs.microsoft.com/samples yardımcı olan bazı meta verilerle başlamalıdır.

> [!div class="nextstepaction"]
> [Chsh-Game örneğinin nasıl oluşturulduğunu görün](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

Bu meta veriler, örneklerinizin hangi dilleri kapsadığını belirten bir [YAML üst bilgisi](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) olarak sağlanır (genellikle bu `qsharp`, `csharp`ve `python`) ve örneklerinizin hangi ürünleri kapsadığını (genellikle, yalnızca `qdk`) gösterir.

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> Docs.microsoft.com/samples adresinde görünmesi için üstbilgideki `page_type: sample` anahtarı gereklidir.
> Benzer şekilde, `product` ve `language` anahtarları, kullanıcıların örneğinizi bulmasına ve çalıştırmasına yardımcı olmak için önemlidir.

Bundan sonra, yeni örneklerinizin ne yaptığını belirten kısa bir giriş sağlamak yararlı olur:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

Ayrıca, örneklerinizin kullanıcıları bu uygulamayı çalıştırmak için gerekenleri de daha da bilir (ör. kullanıcıları yalnızca hisse alım geliştirme paketine ihtiyaç duyar veya Node. js gibi ek yazılımlara gerek duyuyor musunuz?):

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

Her türlü yerde, kullanıcılara örneğinizi nasıl çalıştıracağınızı söyleyebilirsiniz:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

Son olarak, kullanıcılara örnekteki her bir dosyanın ne yaptığını ve daha fazla bilgi için nereye gidebileceklerini söylemek yararlı olur:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> Örneğiniz docs.microsoft.com/samples adresinde işlendiğinde farklı bir URL 'de göründüğünden, burada mutlak URL 'Leri kullandığınızdan emin olun!
