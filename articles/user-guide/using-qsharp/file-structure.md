---
title: 'Q # dosya yapısı'
description: 'Bir Q # dosyasının yapısını ve sözdizimini açıklar.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: 54efc2b9d6b7f1956cdf9a335c88620b29f7729d
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884182"
---
# <a name="q-file-structure"></a>Q # dosya yapısı

Bir Q # dosyası, bir dizi *ad alanı bildirimi*içerir.
Her ad alanı bildirimi, Kullanıcı tanımlı türler, işlemler ve işlevler için bildirimler içerir ve her bir tür bildirime ve herhangi bir sıraya sahip olabilir.
Bir ad alanı içindeki bildirimler hakkında daha fazla bilgi için bkz. [Kullanıcı tanımlı türler](xref:microsoft.quantum.guide.types#user-defined-types), [işlemler](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)ve [işlevler](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).

Bir ad alanı bildiriminin dışında görünebilen tek metin açıklamalardır.
Özellikle, bir ad alanı için bildirim öncesinde belge açıklamaları. Daha fazla bilgi için bu makaledeki [belge açıklamaları](#documentation-comments) bölümüne bakın. 

## <a name="namespace-declarations"></a>Ad alanı bildirimleri

Bir Q # dosyası genellikle yalnızca bir ad alanı bildirimine sahiptir, ancak None (ve boş olabilir ya da yalnızca açıklama içeremez) veya birden çok ad alanı içerebilir.
Ad alanı bildirimleri iç içe olamaz.

Aynı ada sahip hiçbir tür, işlem veya işlev bildirimi olmadığı sürece, birlikte derlenen birden fazla Q # dosyasında aynı ad alanını bildirebilirsiniz.
Özellikle, bildirimler özdeş olsa bile, birden çok dosyada aynı ad alanında aynı türü tanımlamak geçersizdir.

Bir ad alanı bildirimi, anahtar sözcüğünden `namespace` ve ardından ad alanının adı ve küme ayraçları içine alınmış ad alanında yer alan bildirimlerin oluşur `{ }` .
Ad alanı adları, noktalarla ayrılmış bir veya daha fazla yasal sembol dizisinin .NET örüntüsünün izler `.` .
Örneğin, `MyQuantumStuff` ve `Microsoft.Quantum.Intrinsic` geçerli ad alanı adlardır.
Kurala göre, bir ad alanı adında sembolleri büyük harfle yapın, ancak bu gerekli değildir.

Bir dosyada düzgün şekilde tanımlanan türlerin veya callabların başvuruları doğru bir şekilde çözümlenir; bir başvurunun önüne geçmek için tür, işlem veya işlev bildirimine gerek yoktur.

## <a name="open-directives"></a>Açık yönergeler

Bir ad alanı bloğunda, `open` belirli bir ad alanında belirtilen tüm türleri ve callabları içeri aktarmak için yönergesini kullanın ve bunları nitelenmemiş adlarıyla inceleyin.
Bu tür bir `open` yönerge, `open` anahtar sözcüğünden, ardından açılacak ad alanı ve bir sona noktalı virgül içerir.

> [!NOTE] 
> Tüm `open` yönergeler `function` `operation` `newtype` ad alanı bloğunda, veya bildirimlerinden önce gelmelidir.

İsteğe bağlı olarak, açılan ad alanı için kısa bir ad tanımlayabilirsiniz. Kısa bir ad tanımlanmışsa, bu ad alanındaki tüm öğeleri tanımlanmış kısa ad ile nitelemeniz gerekir. Örneğin, aşağıdaki ad alanı bildirimi ve açık yönergeler verildiğinde,

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

tanımlı bir işlem öğesinden bir işlem kullanıyorsa `Op` `Microsoft.Quantum.Intrinsic` , bunu kullanarak çağırın `Op` .
Ancak, ' den belirli bir işlevi çağırmak için `Fn` `Microsoft.Quantum.Math` öğesini kullanarak çağırmanız gerekir `Math.Fn` .

`open`Yönerge, bir dosya içindeki tüm ad alanı bloğunun tamamına uygulanır.
Bu nedenle, aynı Q # dosyasında daha önce ek bir ad alanı tanımlarsanız, bu durumda, `NS` ikinci ad alanında tanımlanan tüm işlemler/işlevler/türler, `Microsoft.Quantum.Intrinsic` `Microsoft.Quantum.Math` içindeki açık yönergeleri tekrarlamazsanız veya hiçbir şeye erişemez. 

Geçerli ad alanında *açılmayan* başka bir ad alanında tanımlanan bir türe veya çağrılabilir öğesine başvurmak için, tam adı ile ona başvurmanız gerekir.
Örneğin, ad alanından adlı bir işlem verilince `Op` `X.Y` :

* `X.Y.Op` `X.Y` Ad alanı geçerli blokta daha önce açılmamışsa, bu ada tam adı ile başvurmanız gerekir. 
* `X`Ad alanı açılmış olsa da, işleme olarak başvurmak mümkün değildir `Y.Op` .
* `Z` `X.Y` Bu ad alanında ve dosyada için kısa ad tanımladıysanız, olarak başvurmanız gerekir `Op` `Z.Op` . 

Bir yönergesi kullanarak bir ad alanı eklemek genellikle daha iyidir `open` .
İki ad alanı aynı ada sahip yapıları tanımladıysa ve geçerli kaynak yapıları her ikisiyle kullanıyorsa, tam nitelikli ad kullanılması gerekir.

Q #, diğer .NET dilleri olarak adlandırmayla aynı kuralları izler.
Ancak, Q # ad alanlarına göreli başvuruları desteklemez.
Örneğin, ad alanı `a.b` açıksa adlı bir işleme başvuru, `c.d` tam ada sahip bir işleme *çözümlenmez* `a.b.c.d` .

## <a name="formatting"></a>Biçimlendirme

Çoğu Q # deyimi ve yönergeleri sonlandırma noktalı virgülle biter `;` .
Ve gibi deyimler ve bildirimler `for` `operation` bir deyim bloğu ile biter (aşağıdaki bölüme bakın) sonlandırma noktalı virgül gerektirmez.
Her bir ifade açıklaması, Sonlandırıcı noktalı virgülden gerekli olup olmadığını not edin.

İfadeler, bildirimler ve yönergeler gibi deyimler birden çok satıra ayrılabilir.
Birden çok deyimi tek bir satıra yerleştirmekten kaçının.

## <a name="statement-blocks"></a>Ekstre blokları

Q # deyimleri, küme ayraçları ile birlikte bulunan deyim blokları halinde gruplandırılır `{ }` . Bir ifade bloğu bir açma ile başlar `{` ve kapanış ile biter `}` .

Başka bir blok içinde Sözcüksel olarak bulunan bir ifade bloğu, kapsayan bloğun bir alt bloğu olarak kabul edilir; içerilen ve alt bloklara dış ve iç bloklar de denir.

## <a name="comments"></a>Yorumlar

Açıklamalar iki eğik çizgi ile başlar `//` ve satırın sonuna kadar devam eder.
Bir soru, Q # kaynak dosyasında herhangi bir yerde görünebilir.

## <a name="documentation-comments"></a>Belge Açıklamaları

Üç eğik çizgi ile başlayan yorumlar, `///` bir ad alanı, işlem, özelleştirme, işlev veya tür tanımından hemen önce göründüğü zaman derleyici tarafından özellikle değerlendirilir.
Bu durumda, derleyici, tanımlı çağrılabilir veya Kullanıcı tanımlı tür için diğer .NET dilleri ile aynı şekilde bir belge olarak davranır.

`///`Açıklamalar içinde, API belgelerinin bir parçası olarak görünen metin, özel olarak adlandırılan üstbilgiler tarafından belirtilen farklı kısımlarla [markaşağı](https://daringfireball.net/projects/markdown/syntax)olarak biçimlendirilir.
Markaşağı içinde, `@"<ref target>"` uzantı çapraz başvuru işlemleri, işlevler ve Kullanıcı tanımlı türler Için Q # kullanın. `<ref target>`Başvurulan kod nesnesinin tam adı ile değiştirin.
Farklı belge motorları, ek Marki uzantılarını da destekleyebilir.

Örneğin:

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

Aşağıdaki adlar belge açıklaması üst bilgileri olarak geçerlidir.

- **Özet**: bir işlev veya işlemin davranışının kısa bir özeti veya bir türün amacı. Özetin ilk paragrafı, üzerine gelme bilgileri için kullanılır. Düz metin olmalıdır.
- **Açıklama**: bir işlev veya işlemin davranışının açıklaması veya bir türün amacı. Birlikte, Özet ve açıklama işlev, işlem veya tür için üretilen belge dosyasını oluşturur.
  Açıklama, satır içi LaTeX biçimli sembolleri ve denklemleri destekler.
- **Giriş**: bir işlemin veya işlevin giriş kayıt düzeninin açıklaması.
  Giriş kayıt düzeninin her bir öğesini gösteren ek Markup alt bölümleri içerebilir.
- **Output**: bir işlem veya işlev tarafından döndürülen tanımlama grubunun açıklaması.
- **Tür parametreleri**: her genel tür parametresi için bir ek alt bölüm içeren boş bir bölüm.
- **Örnek**: işlem, işlev veya kullanılan tür için kısa bir örnek.
- **Açıklamalar**: işlemin, işlevin veya türün bazı yönlerini açıklayan çeşitli işlemler.
- **Ayrıca bkz**: ilgili işlevleri, işlemleri veya Kullanıcı tanımlı türleri gösteren tam nitelikli adların listesi.
- **Başvurular**: belgelenen öğe için başvuruların ve alıntıların listesi.

## <a name="next-steps"></a>Sonraki adımlar

Q # içindeki [işlemler ve işlevler](xref:microsoft.quantum.guide.operationsfunctions) hakkında bilgi edinin.