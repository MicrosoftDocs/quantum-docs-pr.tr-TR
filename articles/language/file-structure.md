---
title: Dosya yapısı | Microsoft Docs
description: 'Q # dosya yapısı'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 364d353c55bda38f227456909755d13dc7e67080
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821091"
---
# <a name="file-structure"></a>Dosya Yapısı

Bir Q # dosyası, bir dizi ad alanı bildirimi içerir.
Her ad alanı bildirimi, Kullanıcı tanımlı türler, işlemler ve işlevler için bildirimler içerir.
Bir ad alanı bildirimi her bir tür bildirime ve herhangi bir sıraya sahip olabilir.
Bir ad alanı bildiriminin dışında görünebilen tek metin açıklamalardır.
Özellikle, bir ad alanı için bildirim öncesinde belge açıklamaları.

## <a name="namespace-declarations"></a>Ad alanı bildirimleri

Bir Q # dosyası genellikle tam olarak bir ad alanı bildirimine sahip olur, ancak None (ve boş veya yalnızca açıklama içeremez) olabilir veya birden çok ad alanı içerebilir.
Ad alanı bildirimleri iç içe olamaz.

Aynı ad alanı, aynı ada sahip hiçbir tür, işlem veya işlev bildirimi olmadığı sürece birlikte derlenen birden fazla Q # dosyasında da bildirilemez.
Özellikle, bildirimler özdeş olsa bile, birden çok dosyada aynı ad alanında aynı türü tanımlamak geçersizdir.

Bir ad alanı bildirimi, anahtar sözcüğünden `namespace`, ardından ad alanının adı, açık bir küme ayracı `{`, ad alanında yer alan bildirimler ve bir kapalı ayraç `}`oluşur.
Ad alanı adları, `.`noktalarla ayrılmış bir veya daha fazla yasal sembol dizisinin .NET örüntüsünün izler.
Örneğin, `MyQuantumStuff` ve `Microsoft.Quantum.Canon` geçerli ad alanı adlarıdır.
Kurala göre, bir ad alanı adındaki semboller büyük harfli olur, ancak bu gerekli değildir.

Bildirimler, bir ad alanı bildiriminde herhangi bir sırada görünebilir.
Bir dosyada daha fazla bildirimde bulunan türlerin veya sabit labların başvuruları düzgün şekilde çözümlenir; bir başvurunun önüne geçmek için tür, işlem veya işlev bildirimine gerek yoktur.

## <a name="open-directives"></a>Açık yönergeler

Bir ad alanı bloğunda, belirli bir ad alanında tanımlanan tüm türleri ve callabları içeri aktarmak için `open` yönergesi kullanılabilir ve bunlara nitelenmemiş adlarıyla başvurabilirler. 

Böyle bir `open` yönergesi `open` anahtar sözcüğünden, ardından açılacak ad alanı ve bir sonlandırma noktalı virgülünden oluşur.

Örneğin,

```qsharp
open Microsoft.Quantum.Canon;
```

İsteğe bağlı olarak, açık ad alanı için bir kısa ad, bu ad alanındaki tüm öğelerin tanımlanmış kısa ad ile nitelendirilerek (ve gerek olması) tanımlanabilir. Bu tür bir kısa ad, bir `open` yönergesinde noktalı virgülden önce istenen kısa ad anahtar sözcüğü eklenerek `as` tanımlanır:

```qsharp
open Microsoft.Quantum.Math as Math;
```

Tüm `open` yönergeleri, ad alanı bloğunda `function`, `operation`veya `newtype` bildirimlerinden önce gelmelidir.
`open` yönergesi, bir dosya içindeki tüm ad alanı bloğunun tamamına uygulanır.

## <a name="user-defined-type-declarations"></a>Kullanıcı tanımlı tür bildirimleri

Q #, kullanıcıların, [Q # tür modeli](xref:microsoft.quantum.language.type-model) bölümünde açıklandığı gibi Kullanıcı tanımlı yeni türler bildirmesi için bir yol sağlar.
Temel türler özdeş olsa bile Kullanıcı tanımlı türler farklıdır.
Özellikle, temeldeki türler özdeş olsa bile, iki Kullanıcı tanımlı türün değerleri arasında otomatik dönüşüm yoktur.

Kullanıcı tanımlı tür bildirimi, anahtar sözcüğünden `newtype`, ardından Kullanıcı tanımlı türün adı, bir `=`, geçerli bir tür belirtimi ve sonlandırma noktalı virgülünden oluşur.

Örneğin:

```qsharp
newtype PairOfInts = (Int, Int);
```

Her Q # kaynak dosyası herhangi bir sayıda kullanıcı tanımlı tür bildirebilir.
Tür adları ad alanı içinde benzersiz olmalıdır ve işlem ve işlev adlarıyla çakışmayabilir.

Kullanıcı tanımlı türler arasında döngüsel bağımlılıklar tanımlamak mümkün değildir. Bu nedenle, özyinelemeli türler Q # içinde mümkün değildir.

## <a name="operation-declarations"></a>İşlem bildirimleri

İşlemler, yaklaşık olarak diğer dillerdeki işlevlere benzeyen Q # ' ın temel sayısıdır.
Her Q # kaynak dosyası herhangi bir sayıda işlem tanımlayabilir.

İşlem adları ad alanı içinde benzersiz olmalıdır ve tür ve işlev adlarıyla çakışmayabilir.

İşlem bildirimleri, anahtar `operation`sözcüğünden ve sonra işlemin adı olan sembol tarafından, işlem için bağımsız değişkenleri tanımlayan türü belirtilmiş bir tanımlayıcı tanımlama grubu, iki nokta üst üste `:`, işlemin sonuç türünü tanımlayan bir tür ek açıklaması, isteğe bağlı olarak işlem ile ilgili bir ek açıklama, bir açık ayraç `{`, işlem bildiriminin gövdesini ve son kapanış ayracı `}`içerir.

İşlem bildiriminin gövdesi, varsayılan uygulamadan ya da bir uzmanlık listesinden oluşur.
Varsayılan gövde özelleştirmesi yalnızca uygulamanın açıkça belirtilmesi gerekiyorsa, varsayılan uygulama doğrudan bildirim içinde belirtilebilir.
Bu durumda, bildirimdeki işlem özelliklerine sahip bir ek açıklama derleyicinin varsayılan uygulamayı temel alarak diğer özelleştirilmiş oluşturmaları otomatik olarak oluşturması için yararlıdır. 

Örneğin: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

İşlem özellikleri, hangi tür nesnelerin beyan edilen işleme uygulanabileceğini ve sahip oldukları etkiyi tanımlar. Bir işlem Unitary dönüştürmesi uygularsa, *adjointed* veya *denetimli*olduğunda işlemin nasıl davrandığını tanımlamak mümkündür.
Bu uzmanlıklar, işlem imzasının bir parçası olarak bildirilebilecek. Bu tür örtülü olarak tanımlanmış her özelleştirme için karşılık gelen uygulama derleyici tarafından oluşturulur. Yukarıdaki örnekte, derleyici tarafından bir adjoint, denetimli ve denetlenen bir adjoint özelleştirmesi oluşturulur. 

Uygulamanın derleyici tarafından üretilebileceği durumda, açıkça belirtilebilir. Bu tür açık Özelleştirme bildirimleri, belirli bir özelleşmenin nasıl derlenildiği veya Kullanıcı tanımlı bir uygulamanın nasıl oluşturulacağını açıklığa kavuşturacak uygun bir oluşturma yönergesi olabilir. Örneğin, yukarıdaki `PrepareEntangledPair` kod, açık özelleştirme bildirimlerini içeren aşağıdaki koda eşdeğerdir: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
Anahtar sözcüğü `auto`, derleyicinin özelleşme uygulamasının nasıl oluşturulacağını belirlemesi gerektiğini belirtir.
Derleyici, daha kesin bir oluşturma yönergesi gibi ek yönergeler olmadan belirli bir özelleşmeye yönelik uygulamayı üretemiyor veya daha verimli bir uygulama verilirse, uygulama da el ile tanımlanabilir.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```

Yukarıdaki örnekte, `adjoint invert;`, adjoint özelleşmesinin gövde uygulamasını tersine getirerek oluşturulacağını ve `controlled adjoint invert;` denetlenen majoint özelleşmesinin, denetlenen özelleşmenin belirtilen uygulamasını tersine ayırarak oluşturulacağını belirtir.

`Adjoint` ve/veya `Controlled` functor uygulamasını desteklemeye yönelik bir işlemin, dönüş türünün `Unit`olması gerekir. 


### <a name="explicit-specialization-declarations"></a>Açık Özelleştirme bildirimleri

S # işlemleri aşağıdaki açık özelleştirme bildirimlerini içerebilir:

- `body` özelleştirmesi, hiçbir komik uygulanmamış şekilde işlemin uygulanmasını belirtir.
- `adjoint` özelleştirmesi, `Adjoint` functor uygulanmış işlemin uygulanmasını belirtir.
- `controlled` özelleştirmesi, `Controlled` functor uygulanmış işlemin uygulanmasını belirtir.
- `controlled adjoint` özelleştirmesi, her iki `Adjoint` ve `Controlled` funtorları ile işlemin uygulanmasını belirtir.
  Bu özelleşme, iki komik bir şekilde `adjoint controlled`de adlandırılmış olabilir.


Bir işlem özelleştirmesi, özelleştirme etiketinden (örn. `body`veya `adjoint`, vb.) sonra aşağıdakilerden birini içerir:

- Aşağıda açıklandığı gibi açık bir bildirim.
- Derleyiciye özelleştirmenin nasıl oluşturulacağını belirten bir yönerge, aşağıdakilerden biri:
  - `intrinsic`, özelleşmenin hedef makine tarafından sağlandığını gösterir.
  - `distribute`, `controlled` ve `controlled adjoint` uzmanlarıyla birlikte kullanılabilir.
    `controlled`ile kullanıldığında, derleyicinin, `body`tüm işlemlere `Controlled` uygulayarak özelleştirmeyi hesaplaması gerektiğini belirtir.
    `controlled adjoint`ile kullanıldığında, derleyicinin özelleştirmeyi `adjoint` özelleşmesinin tüm işlemlerine `Controlled` uygulayarak hesaplaması gerektiğini belirtir.
  - `invert`, derleyicinin `adjoint` özelleştirmesinin `body`ters çevirerek, örneğin işlem sırasını ters çevirerek ve Adjoint öğesini her birine uygulayarak hesapladığını belirten.
    `adjoint controlled`ile kullanıldığında, derleyicinin özelleştirmeyi `controlled` özelleştirmeyi tersine getirerek hesaplaması gerektiğini belirtir.
  - `self`, adjoint özelleşmenin `body` özelleştirmesi ile aynı olduğunu gösterir.
    Bu, `adjoint` ve `adjoint controlled` özelleştirmeler için geçerlidir.
    `adjoint controlled`için, `self` `adjoint controlled` özelleşmenin `controlled` özelleştirmesi ile aynı olduğunu gösterir.
  - `auto`, derleyicinin uygulanacak uygun bir yönergeyi seçmesini belirtmek için.
    `auto` `body` özelleştirmesi için kullanılamayabilir.

Yönergelerin ve `auto` tümünün bir kapanış noktalı virgül `;`gerekir.
`auto` yönergesi, `body` açık bildirimi sağlandıysa aşağıdaki nesil yönergesiyle çözümlenir:

- `adjoint` özelleştirmesi yönerge `invert`göre oluşturulur.
- `controlled` özelleştirmesi yönerge `distribute`göre oluşturulur.
- `adjoint controlled` özelleştirmesi, bir `controlled` açık bildirimine verilse ancak `adjoint`için yoksa ve `distribute` istemiyorsanız, yönergeye göre oluşturulur `invert`.

> [!TIP]   
> Bir işlem kendi kendine adekiyiyiyorsa, derleyicinin en iyi duruma getirme amacıyla bu bilgileri kullanmasına izin vermek için, oluşturma `self` yönergesi aracılığıyla adjoint veya denetimli adjoint özelleşmesini açıkça belirtin.

Kullanıcı tanımlı bir uygulama içeren bir özelleştirme bildirimi, bir bağımsız değişken kayıt kümesinden ve ardından, özelleştirmeyi uygulayan Q # koduna sahip bir ekstre bloğundan oluşur.
Bağımsız değişken listesinde, bir bütün olarak işlem için belirtilen bağımsız değişkenleri temsil etmek üzere `...` kullanılır.
`body` ve `adjoint`için bağımsız değişken listesi her zaman `(...)`olmalıdır; `controlled` ve `adjoint controlled`için bağımsız değişken listesi, denetim qubits dizisini temsil eden bir sembol olmalıdır ve sonra parantez içine alınmış `...`. Örneğin, `(controls,...)`.

Varsayılan gövdenin yanı sıra bir veya daha fazla özelleştirilmiş açıkça bildirilmesi gerekiyorsa, varsayılan gövdeye yönelik uygulamanın uygun bir özelleştirme bildirimine de sarmalanması gerekir:

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="adjoint"></a>Adjoint

Bir işlemin adjoint işlemi, işlemin karmaşık eşlenmesinin nasıl uygulandığını belirtir, yani "ters bir şekilde Çalıştır" durumunda işlem nasıl çalışır.
Adjoint olmadan bir işlem belirtmek geçerlidir; Örneğin, ölçüm işlemlerinde hiçbir adjoint yoktur çünkü bunlar ters çevrilebilir değildir.
Bir işlem, bir adjoint özelleştirmesi için örtük veya açık bir bildirim içeriyorsa, functor `Adjoint` destekler.
Açıkça tanımlanmış denetimli bir adjoint özelleştirmesi bir adjoint özelleşmenin varlığını gösterir. 

Gövdesi, yineleme-Until-başarılı döngüleri, set deyimlerini, ölçümleri, return deyimlerini veya `Adjoint` functor desteklemeyen diğer işlemlere yapılan çağrıları, `invert` veya `auto` yönergesini takip eden bir adjoint özelleşmenin otomatik olarak üretilmesine neden olan işlem için kullanılamaz.

### <a name="controlled"></a>Tarafından

Bir işlemin denetlenen sürümü işlemin ücretlendirilenen bir sürümünün nasıl uygulandığını belirtir, yani bir işlem, bir hisse kayıt durumuna göre uygulandıklarında nasıl davranır.
[Denetlenen](xref:microsoft.quantum.language.type-model#controlled) bölümde daha kapsamlı bir açıklama verilmiştir.

Denetlenen sürüm olmadan bir işlem belirtmek geçerlidir; Örneğin, ölçüm işlemlerinde denetlenebilir olmadığından, denetlenen bir sürüm yoktur.
Bir işlem, yalnızca bildirimi denetimli bir özelleşmenin örtük veya açık bir bildirimini içeriyorsa, `Controlled` functor 'ı destekler.
Açıkça tanımlanmış denetlenen bir adjoint özelleştirmesi, denetimli bir özelleştirmenin varlığını gösterir. 

Gövdesi `Controlled` functor desteklemeyen diğer işlemlere çağrı içeren bir işlem için, `distribute` veya `auto` yönergesinin ardından denetimli bir özelleşmenin otomatik olarak oluşturulması mümkün değildir.

### <a name="controlled-adjoint"></a>Kontrollü adjoint

Bir işlemin kontrollü adjoint sürümü, işlemin adjoint öğesinin hisse kontrollü bir sürümünün nasıl uygulandığını belirtir.
Denetlenen adjoint sürümü olmayan bir işlem belirtmek için geçerlidir; Örneğin, ölçüm işlemlerinde denetlenebilir veya ters çevrilebilir olmadıkları için denetimli bir adjoint sürümü yoktur.

Bir işlem için denetimli bir adjoint özelleştirmesi, ve yalnızca bir adjoint ve denetimli bir özelleştirme varsa var olmalıdır. Bu durumda, denetimli adjoint özelleşmenin varlığı algılanır ve hiçbir uygulama açıkça tanımlanmazsa derleyici tarafından uygun bir özelleştirme oluşturulur. 

Gövdesi denetimli bir adjoint sürümüne sahip olmayan diğer işlemlere çağrı içeren bir işlem için, `invert`bir adjoint özelleştirmesi otomatik olarak oluşturulur `distribute` veya `auto` yönergesi mümkün değildir.


### <a name="examples"></a>Örnekler

İşlem bildirimi, temel Pauli X işlemini tanımlayan aşağıdaki kadar basit olabilir:

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

Aşağıda teleport işlemi tanımlanmaktadır.

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation EPR (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        EPR(target, ancilla);

        // Do the teleportation
        Adjoint EPR (ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a>İşlev bildirimleri

İşlevler, Q # içinde tamamen klasik yordamlardır.
Her Q # kaynak dosyası herhangi bir sayıda işlev tanımlayabilir.

Bir işlev bildirimi, anahtar sözcüğünden `function`, ardından işlevin adı, türü belirlenmiş bir tanımlayıcı tanımlama grubu, işlevin dönüş türünü açıklayan bir tür ek açıklaması ve işlevin uygulamasını tanımlayan bir ifade bloğu içerir.

Bir işlevi tanımlayan ifade bloğunun `{` ve diğer tüm ifade blokları gibi `}` alınması gerekir.

İşlev adları bir ad alanı içinde benzersiz olmalıdır ve işlem ve tür adlarıyla çakışmayabilir.
İşlevler, qubits veya çağrı işlemleri ayıramayabilir. İşlemlerin kısmi uygulaması veya işleme ile yazılan değerler arasında geçiş yapmak iyidir.

Örneğin,

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```
