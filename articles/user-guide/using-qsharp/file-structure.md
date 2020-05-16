---
title: 'Q # dosya yapısı'
description: 'Bir Q # dosyasının yapısını ve sözdizimini açıklar.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: cbee92c6d7e765237a7a42532dd7012b51421708
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430977"
---
# <a name="q-file-structure"></a>Q # dosya yapısı

Her Q # işlem, işlev ve Kullanıcı tanımlı tür bir ad alanı içinde tanımlanır.

Bir Q # dosyası, bir dizi *ad alanı bildirimi*içerir.
Her ad alanı bildirimi, Kullanıcı tanımlı türler, işlemler ve işlevler için bildirimler içerir.
Bir ad alanı bildirimi her bir tür bildirime ve herhangi bir sıraya sahip olabilir.
Bir ad alanı içindeki [Kullanıcı tanımlı türler](xref:microsoft.quantum.guide.types#user-defined-types), [işlemler](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)ve [işlevleri](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) bildirme hakkında daha fazla bilgi için bu bağlantıları izleyin.

Bir ad alanı bildiriminin dışında görünebilen tek metin açıklamalardır.
Özellikle, bildirim öncesinde bir ad alanı için belge açıklamaları (daha fazla ayrıntı).

## <a name="namespace-declarations"></a>Ad alanı bildirimleri

Bir Q # dosyası genellikle tam olarak bir ad alanı bildirimine sahip olur, ancak None (ve boş veya yalnızca açıklama içeremez) olabilir veya birden çok ad alanı içerebilir.
Ad alanı bildirimleri iç içe olamaz.

Aynı ad alanı, aynı ada sahip hiçbir tür, işlem veya işlev bildirimi olmadığı sürece birlikte derlenen birden fazla Q # dosyasında da bildirilemez.
Özellikle, bildirimler özdeş olsa bile, birden çok dosyada aynı ad alanında aynı türü tanımlamak geçersizdir.

Bir ad alanı bildirimi, anahtar sözcüğünden `namespace` , ardından ad alanının adı, açık bir küme ayracı, `{` ad alanında yer alan bildirimler ve bir kapalı ayraç oluşur `}` .
Ad alanı adları, noktalarla ayrılmış bir veya daha fazla yasal sembol dizisinin .NET örüntüsünün izler `.` .
Örneğin, `MyQuantumStuff` ve `Microsoft.Quantum.Intrinsic` geçerli ad alanı adlardır.
Kurala göre, bir ad alanı adındaki semboller büyük harfli olur, ancak bu gerekli değildir.

Bir dosyada daha fazla bildirimde bulunan türlerin veya sabit labların başvuruları düzgün şekilde çözümlenir; bir başvurunun önüne geçmek için tür, işlem veya işlev bildirimine gerek yoktur.

## <a name="open-directives"></a>Açık yönergeler

Bir ad alanı bloğunda, `open` yönerge, belirli bir ad alanında belirtilen tüm türleri ve callabları içeri aktarmak ve bunları nitelenmemiş adlarıyla ifade etmek için kullanılabilir.
Bu tür bir `open` yönerge, `open` anahtar sözcüğünden, ardından açılacak ad alanı ve bir sona noktalı virgül içerir.

> [!NOTE] 
> Tüm `open` yönergeler `function` `operation` `newtype` ad alanı bloğunda, veya bildirimlerinden önce gelmelidir.

İsteğe bağlı olarak, açık ad alanı için bir kısa ad, bu ad alanındaki tüm öğelerin tanımlanmış kısa ad ile nitelendirilerek (ve gerek olması) tanımlanabilir. Örneğin, aşağıdaki ad alanı bildirimi ve açık yönergeler verildiğinde,

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

bildirdiğimiz bir işlem öğesinden bir işlem kullanıyorsa `Op` `Microsoft.Quantum.Intrinsic` , bunu yalnızca kullanarak çağıracağız `Op` .
Ancak, ' den belirli bir işlevi çağırmayı istiyorduk `Fn` `Microsoft.Quantum.Math` , kullanarak çağırırız `Math.Fn` .

`open`Yönerge, bir dosya içindeki tüm ad alanı bloğunun tamamına uygulanır.
Bu nedenle, yukarıdaki aynı Q # dosyasında ek bir ad alanı tanımlıyoruz `NS` , ikinci ad alanında tanımlanan tüm işlemler/işlevler/türler, `Microsoft.Quantum.Intrinsic` `Microsoft.Quantum.Math` içindeki açık yönergeleri tekrarlamadığı sürece veya ' den herhangi bir şeye erişemez. 

Geçerli ad alanında açılmamış başka bir ad alanında tanımlanan bir tür veya *çağrılabilir, tam* nitelikli ad tarafından başvurulmalıdır.
Örneğin, ad alanı `Op` `X.Y` `X.Y.Op` `X.Y` geçerli blokta daha önce açılmamışsa, ad alanından adlı bir işleme tam nitelikli adıyla başvurulmalıdır. Yukarıda belirtildiği gibi, `X` ad alanı açılmış olsa da, işleme olarak başvurmak mümkün değildir `Y.Op` .
İçin kısa bir ad `Z` `X.Y` , bu ad alanında ve dosyada tanımlanmışsa, `Op` olarak adlandırılmaları gerekir `Z.Op` . 

Bir yönergesi kullanarak bir ad alanı eklemek genellikle daha iyidir `open` .
İki ad alanı aynı ada sahip yapıları tanımladıysa ve geçerli kaynak yapıları her ikisiyle kullanıyorsa, tam nitelikli ad kullanılması gerekir.

Q #, diğer .NET dilleri olarak adlandırmayla aynı kuralları izler.
Ancak, Q # ad alanlarına göreli başvuruları desteklemez.
Diğer bir deyişle, ad alanı `a.b` açıldıysa, adlı bir işlem için bir başvuru, `c.d` tam ada *not* sahip bir işleme çözümlenmeyecektir `a.b.c.d` .

## <a name="formatting"></a>Biçimlendirme

Çoğu Q # deyimi ve yönergeleri sonlandırma noktalı virgülle biter `;` .
Ve gibi deyimler ve bildirimler `for` `operation` bir deyim bloğu (aşağıya bakın) ile biten bir bitiş noktalı virgül gerektirmez.
Her bir ifade açıklaması, Sonlandırıcı noktalı virgülden gerekli olup olmadığını not edin.

İfadeler, bildirimler ve yönergeler gibi deyimler birden çok satıra ayrılabilir.
Tek bir satırda birden çok deyimin olması kaçınılmalıdır.

## <a name="statement-blocks"></a>Ekstre blokları

Q # deyimleri deyim blokları halinde gruplandırılır.
Bir ifade bloğu bir açma ile başlar `{` ve kapanış ile biter `}` .

Başka bir blok içinde Sözcüksel olarak bulunan bir ifade bloğu, kapsayan bloğun bir alt bloğu olarak kabul edilir; içerilen ve alt bloklara dış ve iç bloklar de denir.

## <a name="comments"></a>Yorumlar

Açıklamalar iki eğik çizgi ile başlar `//` ve satır sonuna kadar devam eder.
Bir soru, Q # kaynak dosyasında herhangi bir yerde görünebilir.

## <a name="documentation-comments"></a>Belge Açıklamaları

Üç eğik çizgi ile başlayan yorumlar, `///` bir ad alanı, işlem, özelleştirme, işlev veya tür tanımından hemen önce göründüğü zaman derleyici tarafından özellikle değerlendirilir.
Bu durumda, içeriği diğer .NET dilleri gibi tanımlanmış çağrılabilir veya Kullanıcı tanımlı tür için belgeler olarak alınır.

`///`Açıklamalar içinde, API belgelerinin bir parçası olarak görünen metin, özel olarak adlandırılmış üst bilgiler tarafından belirtilen belgelerin farklı bölümleriyle [markaşağı](https://daringfireball.net/projects/markdown/syntax)olarak biçimlendirilir.
Markı 'nin bir uzantısı olarak, Q # içindeki işlemlere, işlevlere ve Kullanıcı tanımlı türlere çapraz başvurular kullanılarak dahil edilebilir, `@"<ref target>"` burada, `<ref target>` başvurulan kod nesnesinin tam adı ile değiştirilmiştir.
İsteğe bağlı olarak, bir belge altyapısı ek markı uzantılarını da destekleyebilir.

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

Aşağıdaki adlar belge açıklama üstbilgileri olarak tanınır.

- **Özet**: bir işlev veya işlemin davranışının veya bir tür amacının kısa özeti. Özetin ilk paragrafı, üzerine gelme bilgileri için kullanılır. Düz metin olmalıdır.
- **Açıklama**: bir işlevin veya işlemin davranışının veya bir türün amacının açıklaması. Özet ve açıklama, işlev, işlem veya tür için üretilen belge dosyasını oluşturacak şekilde birleştirilir.
  Açıklama, satır içi LaTeX biçimli sembolleri ve denklemleri içerebilir.
- **Giriş**: bir işlemin veya işlevin giriş kayıt düzeninin açıklaması.
  Giriş kayıt düzeni öğelerinin her birini belirten ek Markup alt bölümleri içerebilir.
- **Output**: bir işlem veya işlev tarafından döndürülen tanımlama grubunun açıklaması.
- **Tür parametreleri**: her genel tür parametresi için bir ek alt bölüm içeren boş bir bölüm.
- **Örnek**: işlemin, işlevin veya tür kullanılan kısa bir örnek.
- **Açıklamalar**: işlemin, işlevin veya türün bazı yönlerini açıklayan çeşitli işlemler.
- **Ayrıca bkz**: ilgili işlevleri, işlemleri veya Kullanıcı tanımlı türleri gösteren tam nitelikli adların listesi.
- **Başvurular**: belgelendirilmekte olan öğe için başvuruların ve alıntıların listesi.

## <a name="whats-next"></a>Sırada Ne Var?
Q # içindeki [işlemler ve işlevler](xref:microsoft.quantum.guide.operationsfunctions) hakkında bilgi edinin.