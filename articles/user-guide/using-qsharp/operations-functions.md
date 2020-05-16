---
title: "Q 'daki işlemler ve işlevler #"
description: İşlem ve işlevlerin yanı sıra denetlenen ve Adjoint işlem uzmanlıklarını tanımlama ve çağırma.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: bc9695b85b68807801225ccbc903a4622b450768
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431079"
---
# <a name="operations-and-functions-in-q"></a>Q 'daki işlemler ve Işlevler #

## <a name="defining-new-operations"></a>Yeni Işlemleri tanımlama

İşlemler, Q # ' ın temel sayısıdır.
Bildirdikten sonra, bir simülatör kullanılarak veya Q # içindeki diğer işlemler tarafından klasik .NET uygulamalarından çağrılabilir.
Q # içinde tanımlanan her işlem, dil tarafından tanımlanan yerleşik iç işlemler de dahil olmak üzere herhangi bir sayıda işlemi çağırabilir. Bu iç işlemlerin tanımlandığı belirli yol, hedef makineye bağlıdır.
Derlendiğinde, her işlem hedef makinelere sağlanlenebilecek bir .NET sınıf türü olarak temsil edilir.

Her Q # kaynak dosyası herhangi bir sayıda işlem tanımlayabilir.
İşlem adları ad alanı içinde benzersiz olmalıdır ve tür veya işlev adlarıyla çakışmayabilir.

İşlem bildirimi, anahtar sözcüğünden ve `operation` ardından işlemin adı olan sembol, işlem için bağımsız değişkenleri tanımlayan türü belirlenmiş bir tanımlayıcı tanımlama grubu, iki nokta üst üste `:` , işlemin sonuç türünü açıklayan bir tür ek açıklaması, isteğe bağlı olarak işlem özelliklerine sahip bir ek açıklama, bir açık küme ayracı `{` , işlem bildiriminin gövdesi ve son kapanış ayracı oluşur `}` .

Her işlem bir girdi alır, bir çıktı üretir ve bir veya daha fazla işlem uzmanlığını için uygulamayı belirtir.
Olası Uzmanlıklar ve bunların nasıl tanımlanacağı/çağrılacağını aşağıda bulabilirsiniz.
Şimdilik yalnızca bir varsayılan gövde özelleştirmesi tanımlayan ve giriş olarak tek bir qubit alan aşağıdaki işlemi göz önünde bulundurun ve sonra <xref:microsoft.quantum.intrinsic.x> Bu girişte yerleşik işlemi çağırır:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

Anahtar sözcüğü `operation` işlem tanımını başlatır ve ardından ad, burada, `BitFlip` .
Sonra, girişin türü `Qubit` , `target` Yeni işlemdeki girişe başvurmak için bir adla birlikte tanımlanır.
Benzer şekilde, `Unit` işlem çıkışının boş olduğunu tanımlar.
Bu, `void` C# ve diğer zorunlu dillerde aynı şekilde kullanılır ve `unit` F # ve diğer işlevsel dillerde eşdeğerdir.

İşlemler Ayrıca, öğesinden daha ilginç türler de döndürebilir `Unit` .
Örneğin, işlem, <xref:microsoft.quantum.intrinsic.m> `Result` ölçüm gerçekleştirmemiş olduğunu temsil eden türünde bir çıktı döndürür. Bir işlemden çıkışı başka bir işleme geçirebiliriz ya da `let` Yeni bir değişken tanımlamak için anahtar sözcükle birlikte kullanabilirsiniz.

Bu, [yoğun kodlama](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)gibi düşük bir düzeyde hisse uygun olan klasik hesaplamayı temsil etmenizi sağlar:

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> Q # içindeki her işlem tam olarak bir giriş alır ve tam olarak bir çıkış döndürür.
> Birden çok giriş ve çıkış daha sonra birden çok değeri tek bir değerde toplamak için *Tanımlama grupları*kullanılarak temsil edilir.
> Bu durumda, Q # ' ın bir "demet oluşturma" dili olduğunu varsayalım.
> Bu kavram sonrasında, `()` türü olan "boş" kayıt düzeni olarak okunmalıdır `Unit` .


## <a name="controlled-and-adjoint-operations"></a>Denetlenen ve Adjoint Işlemleri

Bir işlem, bir Unitary dönüştürmesi uygularsa, Q # içindeki birçok işlem için durum olduğu gibi, *adjointed* veya *denetimli*olduğunda işlemin nasıl davrandığını tanımlamak mümkündür. Bir işlemin *adjoint* özelleştirmesi işlemin nasıl davranması gerektiğini belirtir, *denetimli* bir özelleşme, uygulamanın belirli bir hisse kaydı durumunda olduğu durumlarda bir işlemin nasıl davranması gerektiğini belirtir.

Hisse unsurlarının bir bölümünü, hisse bilgi işlem işlemlerinin birçok yönü için çok önemlidir. Aşağıda, [conjugations](#conjugations) bölümünde, yararlı bir Q # programlama tekniğinin yanı sıra ele alınan bir durum bulacaksınız.

Bir işlemin denetlenen sürümü, yalnızca tüm denetim qubits 'in belirtilen durumda olması durumunda temel işlemi etkili bir şekilde uygulayan yeni bir işlemdir.
Denetim qubitleri üst konumundayken, temel işlem üst konumun uygun bölümüne doğru şekilde uygulanır.
Bu nedenle, denetimli işlemler genellikle entanglement oluşturmak için kullanılır.

Doğal olarak, *denetlenen bir adjoint* özelleştirmesi de bir işlemin adjoint öğesinin denetimli uygulamasını belirterek bulunabilir.

> [!NOTE]
> $U $, bir işlem tarafından uygulanan Unitary dönüşümünde `U` , `Adjoint U` karmaşık eşleniği devrik olan "^ \dağılım $ $U Unitary dönüşümünü temsil eder.
> Bir işlemin büyük bir bir şekilde uygulanması ve sonra adekliği, bu durum, $UU ^ \gger = U ^ \gger U = \ID $, kimlik matrisi olan olgu tarafından gösterildiği gibi durumu değişmeden bırakır.
> Denetlenen bir işlemin Unitary temsili biraz daha fazla bir işlemdir, ancak daha fazla ayrıntı için [hisse bilgi işlem kavramlarıyla daha fazla bilgi bulabilirsiniz: birden çok qubit](xref:microsoft.quantum.concepts.multiple-qubits).

Aşağıdaki bölümde, bu çeşitli uzmanların Q # kodunuzda nasıl çağrılacağını açıklanmaktadır.
Aşağıda, bunları desteklemek için işlemlerin nasıl tanımlanacağı ayrıntılandırıyoruz.

### <a name="calling-operation-specializations"></a>İşlem uzmanlık işlemleri çağrılıyor

Q # ' daki bir *functor* , başka bir işlemden yeni bir işlem tanımlayan bir fabrikadır.
Q # içindeki iki standart komik `Adjoint` ve ' dir `Controlled` .

Funörler, yeni işlemin uygulamasını tanımlarken temel işlemin uygulamasına erişebilir.
Bu nedenle, funörler geleneksel daha yüksek düzey işlevlerden daha karmaşık işlevler gerçekleştirebilir. Funörler, Q # tür sisteminde bir gösterimine sahip değildir. Bu nedenle, şu anda bunları bir değişkene bağlamak veya bağımsız değişken olarak geçirmek mümkün değildir. 

Komik bir ctor, bir işleme uygulanarak yeni bir işlem döndürerek kullanılır.
Örneğin, işlem için functor uygulamanın sonucu olan işlem `Adjoint` `Y` olarak yazılır `Adjoint Y` .
Yeni işlem daha sonra başka bir işlem gibi çağrılabilir.
Bir işlemin `Adjoint` ve/veya komik uygulamalarının uygulamasını desteklemesi için `Controlled` dönüş türünün olması gerekir `Unit` . 

#### <a name="adjoint-functor"></a>`Adjoint`functor

Bu nedenle, `Adjoint Y(q1)` `Y` Yeni bir işlem oluşturmak Için adjoint functor işlemini uygular ve bu yeni işlemi öğesine uygular `q1` .
Yeni işlem, temel işlemle aynı imzaya ve türe sahip `Y` .
Özellikle, yeni işlem de izin verir `Adjoint` ve `Controlled` yalnızca temel işlem olduysa, ancak izin verir.
Adjoint functor kendi tersidir; Yani, `Adjoint Adjoint Op` her zaman ile aynıdır `Op` .

#### <a name="controlled-functor"></a>`Controlled`functor

Benzer şekilde, `Controlled X(controls, target)` `X` Yeni bir işlem oluşturmak için denetimli functor işlemini uygular ve bu yeni işlemi ve için uygular `controls` `target` .

> [!NOTE]
> Q # ' da denetimli sürümler her zaman bir denetim qubit dizisini alır ve belirtilen durum her zaman denetim qubits 'in hesaplama ( `PauliZ` ) `One` durumunda, $ \gre$ ' da olması için gereklidir {1} .
> Diğer durumlara dayalı olarak denetlemek, denetimli işlemden önce denetim qubits 'e uygun Unitary işlemini uygulayarak ve sonra, denetimli işlemden sonra Unitary işleminin evirimini uygulayarak elde edilebilir.
> Örneğin, `X` denetimli bir işlemden önce ve sonra bir işlemi bir denetim qubit uygulamak, `Zero` Bu qubit için ($ \ket $) durumunda işlemin denetimine neden olur {0} ; durum `H` üzerinde önce ve sonra bir işlemi uygulamak `PauliX` `One` , durum yerine Pauli X, $ \tus\mathrel{ {-} : =} (\tus- {0} \ket {1} )/\sqrt {2} $ `PauliZ` `One` olan-1 eigenvalue.

Bir işlem ifadesi verildiğinde, yeni bir işlem ifadesi `Controlled` functor kullanılarak oluşturulabilir.
Yeni işlemin imzası, özgün işlemin imzasını temel alır.
Sonuç türü aynıdır, ancak giriş türü, ilk öğe olarak denetim qubit dizisini ve ikinci öğe olarak orijinal işlemin bağımsız değişkenlerini tutan bir qubit dizisi olan iki kayıt türüdür.
Yeni işlem `Controlled` ' i destekler ve `Adjoint` yalnızca özgün işlem olduysa, ve yalnızca bunu destekler.

Özgün işlem yalnızca tek bir bağımsız değişken alıyorsa, bu durumda tek demet denklik, burada yürütmeye gelir.
Örneğin, `Controlled X` işlemin denetlenen sürümüdür `X` . 
`X`türüne sahip `(Qubit => Unit is Adj + Ctl)` , `Controlled X` Bu nedenle türüne sahip `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` . tek kayıt düzeni denkliği nedeniyle bu, ile aynıdır `((Qubit[], Qubit) => Unit is Adj + Ctl)` .

Temel işlem birkaç bağımsız değişken alıyorsa, bu işlemin denetlenen sürümünün ilgili bağımsız değişkenlerini, bir tanımlama grubu içine dönüştürmek için parantez içine almayı unutmayın.
Örneğin, `Controlled Rz` işlemin denetlenen sürümüdür `Rz` . 
`Rz`türüne sahip `((Double, Qubit) => Unit is Adj + Ctl)` , bu nedenle `Controlled Rz` türüne sahip `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .
Bu nedenle, `Controlled Rz(controls, (0.1, target))` geçerli bir çağrısı olur `Controlled Rz` (etrafındaki ayraçları aklınızda bulunan `0.1, target` ).

Başka bir örnek olarak, `CNOT(control, target)` olarak uygulanabilir `Controlled X([control], target)` . Bir hedef 2 denetim qubits (CCNOT) tarafından denetleniyorsa, ifadesini kullanabiliriz `Controlled X([control1, control2], target)` .

#### `Controlled Adjoint` 

`Controlled`Ve `Adjoint` komik, ve uygulama arasında bir fark yoktur `Controlled Adjoint Op` `Adjoint Controlled Op` .


## <a name="defining-controlled-and-adjoint-implementations"></a>Denetlenen ve Adjoint uygulamalarını tanımlama

Yukarıdaki ilk işlem bildirimi örneklerinde, işlemler `BitFlip` ve `DecodeSuperdense` sırasıyla imzalar ve ile tanımlanmıştır `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` .
`DecodeSuperdense`Ölçümler de dahil olmak üzere, Unitary bir işlem değildir ve bu nedenle hiçbir adeksel uzmanlık yok (Bu, bu tür bir işlemin döndürdüğü ilgili gereksinimi geri çağırır `Unit` ).
Ancak, `BitFlip` yalnızca Unitary işlemini gerçekleştirdiğinden, <xref:microsoft.quantum.intrinsic.x> her iki uzmanlıklarla de tanımlanabilir.

Burada, Q # işlem bildirimlerinizde uzmanlıkların nasıl ekleneceğini ayrıntılandırıyoruz ve bu nedenle, `Adjoint` ve/veya funlar ile birlikte çağrılabilir `Controlled` .
[Aşağıda](#circumstances-for-validly-defining-specializations), geçerli olduğu veya belirli uzmanlık bildirmek için geçerli olmayan bazı durumlar açıklanır.

İşlem özellikleri, hangi tür nesnelerin beyan edilen işleme uygulanabileceğini ve sahip oldukları etkiyi tanımlar. Bu uzmanlıklardan biri, özellikle işlem özelliklerine sahip bir ek açıklama aracılığıyla işlem imzasının bir parçası olarak bildirilemez: `is Adj` ,, `is Ctl` veya `is Adj + Ctl` .
Her özelleştirmenin gerçek uygulama *örtük* veya *Açık* bir şekilde tanımlanabilir.

### <a name="implicitly-specifying-implementations"></a>Örtük olarak uygulamaları belirtme

Bu durumda, işlem bildiriminin gövdesi yalnızca varsayılan uygulamadan oluşur. Örneğin:

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
Burada, örtük olarak tanımlanmış her bir özelleştirme için karşılık gelen uygulama, veya komik kullanılıyorsa, derleyici tarafından otomatik olarak oluşturulur `Adjoint` `Controlled` .

Bu nedenle, bir çağrısı `Adjoint PrepareEntangledPair` derleyicinin adekini `CNOT` ve sonra adekini uygulamasına neden olur `H` .
Bu bireysel işlemler kendi kendine adekdir, bu nedenle sonuçtaki `Adjoint PrepareEntangledPair` işlem yalnızca uygulama `CNOT(here, there)` ve ardından oluşur `H(here)` .
Bu nedenle `DecodeSuperdense` , `PrepareEntangledPair` entangled durumunu bir qubit çiftiyle geri dönüştürmek için adjoint öğesini kullanarak daha fazla sıkı örneğini yazmak için bunu kullanabiliriz:

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

Bildirimin işlem özellikleriyle birlikte ek açıklama, derleyicinin varsayılan uygulamaya göre diğer özelleştirmeleri otomatik olarak üretmesinin güvence altına almak için yararlıdır. 

Funlar ile kullanım için işlemleri tasarlarken göz önünde bulundurmanız gereken bazı önemli sınırlamalar vardır.
Aynı etkiyi elde etmek için bu tür bir işlemde deyimleri yeniden sıralamak belirsiz olduğundan, başka bir *işlemin çıkış* değerini kullanan bir işlem için en kritik öneme sahip olan uzmanlık, derleyici tarafından otomatik olarak üretilemez.

Bu nedenle, genellikle çeşitli uygulamaları açıkça belirtmek yararlı olur.

### <a name="explicitly-specifying-implementations"></a>Uygulamaları açıkça belirtme

Uygulamanın derleyici tarafından üretilebileceği durumda, açıkça belirtilebilir. Bu tür açık özelleşmeler, uygun bir *oluşturma yönergesinin* veya Kullanıcı tanımlı bir uygulamadan oluşabilir.
Burada aşağıda belirtilen örneklerle birlikte tam olarak çeşitli olanaklar sağlıyoruz.


#### <a name="explicit-specialization-declarations"></a>Açık Özelleştirme bildirimleri

S # işlemleri aşağıdaki açık özelleştirme bildirimlerini içerebilir:

- `body`Özelleşme, hiçbir komik uygulanmamış şekilde işlemin uygulanmasını belirtir.
- `adjoint`Özelleşme, işlem için `Adjoint` functor uygulanmış olan uygulamayı belirtir.
- `controlled`Özelleşme, işlem için `Controlled` functor uygulanmış olan uygulamayı belirtir.
- `controlled adjoint`Özelleşme, hem hem de `Adjoint` funları uygulanan işlemin uygulanmasını belirtir `Controlled` .
  Bu özelleşme `adjoint controlled` , iki komik bulunduğu için de adlandırılmış olabilir.


Bir işlem özelleştirmesi, özelleştirme etiketinden (ör. `body` veya `adjoint` , vb.) sonra aşağıdakilerden birini içerir:

- Aşağıda açıklandığı gibi açık bir bildirim.
- Derleyiciye özelleştirmenin *nasıl* oluşturulacağını belirten bir *yönerge* , aşağıdakilerden biri:
  - `intrinsic`, özelleşmenin hedef makine tarafından sağlandığını gösterir.
  - `distribute`, `controlled` ve `controlled adjoint` uzmanlarıyla kullanılabilecek.
    İle kullanıldığında `controlled` , derleyicinin `Controlled` , içindeki tüm işlemlere uygulanarak özelleştirmeyi hesaplaması gerektiğini belirtir `body` .
    İle kullanıldığında `controlled adjoint` , derleyicinin özelleşmenin tüm işlemlerine uygulayarak özelleştirmeyi hesaplaması gerektiğini belirtir `Controlled` `adjoint` .
  - `invert`Bu, derleyicinin özelleştirmeyi hesaplaması gerektiğini gösterir, `adjoint` `body` Örneğin, işlem sırasını tersine çevirme ve her birine adeki uygulama.
    İle kullanıldığında `adjoint controlled` , bu, derleyicinin özelleştirmeyi ters çeviren şekilde özelleşmesi gerektiğini belirtir `controlled` .
  - `self`, adjoint özelleşmenin özelleşme ile aynı olduğunu göstermek için `body` .
    Bu, `adjoint` ve `adjoint controlled` Uzmanlıklar için geçerlidir.
    İçin `adjoint controlled` , `self` `adjoint controlled` özelleştirmenin özelleştirme ile aynı olduğunu gösterir `controlled` .
  - `auto`, derleyicinin uygulanacak uygun bir yönergeyi seçmesini belirtmek için.
    `auto``body`özelleşme için kullanılamaz.

Yönergelerin ve `auto` tümünün bir kapanış noktalı virgül olması gerekir `;` .
`auto`Yönergesi, bir açık bildirimi sağlanmışsa, aşağıdaki nesil yönergesini çözümler `body` :

- `adjoint`Özelleşme, yönergeye göre oluşturulur `invert` .
- `controlled`Özelleşme, yönergeye göre oluşturulur `distribute` .
- `adjoint controlled` `invert` İçin açık bir bildirime izin `controlled` verilse `adjoint` , ve yoksa, özelleştirme yönergeye göre oluşturulur `distribute` .

> [!TIP]   
> Bir işlem kendi kendine adekiyiyise, `self` derleyicinin en iyi duruma getirme amacıyla bu bilgileri kullanmasına izin vermek için oluşturma yönergesi aracılığıyla adjoint veya denetimli adjoint özelleşmesini açıkça belirtin.

Kullanıcı tanımlı bir uygulama içeren bir özelleştirme bildirimi, bir bağımsız değişken kayıt kümesinden ve ardından, özelleştirmeyi uygulayan Q # koduna sahip bir ekstre bloğundan oluşur.
Bağımsız değişken listesinde, `...` işlem için belirtilen bağımsız değişkenleri bir bütün olarak temsil etmek için kullanılır.
`body`Ve için `adjoint` bağımsız değişken listesi her zaman olmalıdır `(...)` ; ve için `controlled` `adjoint controlled` bağımsız değişken listesi, denetim qubits dizisini temsil eden bir sembol olmalıdır `...` ; Örneğin, parantez içine alınmış `(controls,...)` .

### <a name="examples"></a>Örnekler

İşlem bildirimi, temel Pauli X işlemini tanımlayan aşağıdaki kadar basit olabilir:

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
Pauli X işleminin adjoint değeri, `self` tanım tarafından kendi tersi olduğundan, yönergeyle tanımlandığını unutmayın `X` .

Örneğin, yukarıdaki kod, `PrepareEntangledPair` Açık özelleştirme bildirimlerini içeren aşağıdaki koda eşdeğerdir: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
Anahtar sözcüğü, `auto` derleyicinin nasıl özelleşdiğini uygulamanın nasıl oluşturulacağını belirlemesi gerektiğini belirtir.

#### <a name="user-defined-specialization-implementation"></a>Kullanıcı tanımlı özelleştirme uygulama

Derleyici belirli bir özelleşmenin uygulamasını otomatik olarak üretemiyor veya daha verimli bir uygulama verilirse, uygulama da el ile tanımlanabilir.

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
Yukarıdaki örnekte, `adjoint invert;` adjoint özelleşmesinin gövde uygulamasını tersine çeviren ve denetimli bir `controlled adjoint invert;` adjoint özelleşmesinin, denetlenen özelleşmenin belirtilen uygulamasını tersine ayırarak oluşturulacağını belirtir.

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

### <a name="circumstances-for-validly-defining-specializations"></a>Geçerli uzmanlık belirleme koşulları

#### <a name="operation-declarations-with-adjointcontrolled"></a>Adjoint/kontrollü işlem bildirimleri

Adjoint veya denetimli sürümleri olmayan bir işlem belirtmek için geçerlidir. Örneğin, ölçüm işlemleri tersine çevrilebilir veya denetlenebilir olmadığından, bu işlemler değildir.

Bir işlem, `Adjoint` `Controlled` bildirimi ilgili özelleştirmeler için örtük veya açık bir bildirim içeriyorsa, ve/veya komik oluşturucuları destekler.

Açıkça tanımlanmış bir adjoint/kontrollü özelleştirme, bir adjoint/denetimli özelleştirmenin varlığını gösterir. 

Gövdesi, yineleme-Until-başarılı döngüleri, set deyimlerini, ölçümleri, return deyimlerini veya funı desteklemeyen diğer işlemlere yapılan çağrıları içeren bir işlem için, `Adjoint` veya yönergesini izleyen bir adjoint özelleşmenin otomatik olarak oluşturulması `invert` `auto` mümkün değildir.

Gövdesi, functor desteklemeyen diğer işlemlere çağrı içeren bir işlem için `Controlled` , veya yönergesini izleyen denetimli bir özelleşmenin otomatik olarak oluşturulması `distribute` `auto` mümkün değildir.

#### <a name="controlled-adjoint"></a>Kontrollü adjoint

Bir işlemin kontrollü adjoint sürümü, işlemin adjoint öğesinin hisse kontrollü bir sürümünün nasıl uygulandığını belirtir.
Denetlenen adjoint sürümü olmayan bir işlem belirtmek için geçerlidir; Örneğin, ölçüm işlemlerinde denetlenebilir veya ters çevrilebilir olmadıkları için denetimli bir adjoint sürümü yoktur.

Bir işlem için denetimli bir adjoint özelleştirmesi, ve yalnızca bir adjoint ve denetimli bir özelleştirme varsa var olmalıdır. Bu durumda, denetimli adjoint özelleşmenin varlığı algılanır ve hiçbir uygulama açıkça tanımlanmazsa derleyici tarafından uygun bir özelleştirme oluşturulur. 

Gövdesi denetimli bir adjoint sürümüne sahip olmayan diğer işlemlere çağrı içeren bir işlem için, veya yönergesini izleyen bir adjoint özelleştirmesi otomatik olarak `invert` `distribute` `auto` oluşturulur.


### <a name="type-compatibility"></a>Tür uyumluluğu

Desteklenen ek bir işlem, daha az komik olan bir işlemin her yerde kullanılabilir, ancak aynı imza beklenmektedir.
Örneğin, türünde bir işlem `(Qubit => Unit is Adj)` beklenen her yerde kullanılabilir `(Qubit => Unit)` .

Q #, çağrılabilir dönüş türlerine göre *birlikte değişken* : bir tür döndüren çağrılabilir, `'A` aynı giriş türüne ve ile uyumlu bir sonuç türüne sahip çağrılabilir ile uyumludur `'A` .

S #, giriş türlerine göre *değişken karşıtı:* giriş olarak bir türü alan çağrılabilir, `'A` aynı sonuç türü ve ile uyumlu bir giriş türü olan çağrılabilir ile uyumludur `'A` .

Diğer bir deyişle, aşağıdaki tanımlar verilir:

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

aşağıdakiler doğrudur:

- İşlev `ConjugateInvertWith` `inner` ya da veya bağımsız değişkeniyle çağrılabilir `Invert` `ApplyUnitary` .
- İşlev `ConjugateUnitaryWith` `inner` , bağımsız değişkeniyle çağrılabilir `ApplyUnitary` , ancak değil `Invert` .
- Türünde bir değer `(Qubit[] => Unit is Adj + Ctl)` döndürülebilecek `ConjugateInvertWith` .

> [!IMPORTANT]
> Q # 0,3, Kullanıcı tanımlı türlerin davranışında önemli bir farklılık sunmuştur.

Kullanıcı tanımlı türler, alt tür yerine temel alınan türün Sarmalanan bir sürümü olarak değerlendirilir.
Bu, Kullanıcı tanımlı türün bir değerinin, temel alınan türden bir değerin beklenildiği durumlarda kullanılamaz olduğu anlamına gelir.


### <a name="conjugations"></a>Conjugations

Klasik bitlerin aksine, qubits 'in hala bir daha açık olması durumunda qubits 'in kalan hesaplamada istenmeyen etkileri olabildiğinden, hisse bitlerinin serbest bırakılması biraz daha karmaşıktır. Bu, belleğin serbest bırakılmasından önce düzgün bir şekilde "geri alma" sırasında gerçekleştirilen hesaplamaları önlenebilir. Bu nedenle, hisse kullanımı için genel bir model aşağıda verilmiştir: 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

0,9 sürümümüzden başlayarak, yukarıdaki dönüşümü uygulayan bir Birleşik bildirim bildirisini destekliyoruz. Bu ifadeyi kullanarak, işlem `ApplyWith` aşağıdaki şekilde uygulanabilir:

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
Bu tür bir birleşim deyimi, dış ve iç dönüşüm işlem olarak hazır değilse ancak birkaç deyimden oluşan bir blok tarafından tanımlanmakla daha kullanışlı hale gelirse çok daha yararlıdır. 

İçindeki blok içinde tanımlanan deyimler için ters dönüşüm, derleyici tarafından otomatik olarak oluşturulur ve Apply-Block tamamlandıktan sonra yürütülür.
İçindeki blok içinde kullanılan herhangi bir değişebilir değişken, Apply-Block içinde yeniden bağlanamaz, oluşturulan dönüşümün, hesaplamanın içindeki adeklik olduğu garanti edilir. 


## <a name="defining-new-functions"></a>Yeni Işlevleri tanımlama

İşlevler, bir çıkış değerinin hesaplanmasının dışında etkileri olmasına izin verilmediğinden, işlemlerinden farklı olarak, yalnızca belirleyici olan, bu işlemler olan Q # içindeki klasik yordamlardır.
Özellikle, işlevler işlemleri çağıramaz; işlem yapın, ayırın veya ödünç alma; örnek rastgele sayılar; ya da diğer bir deyişle, giriş değerinin ötesine bir işleve bağımlı duruma bağlıdır.
Sonuç olarak, Q # işlevleri *saf*olduğundan, her zaman aynı giriş değerlerini aynı çıkış değerleriyle eşleştirirler.
Bu, Q # derleyicisinin, işlem uzmanlıklarını oluştururken işlevleri nasıl ve ne zaman çağırdığını güvenle yeniden sıralamak için izin verir.

Her Q # kaynak dosyası herhangi bir sayıda işlev tanımlayabilir.
İşlev adları bir ad alanı içinde benzersiz olmalıdır ve işlem veya tür adlarıyla çakışmayabilir.

Bir işlev tanımlamak, bir işlev için hiçbir adjoint veya denetimli uzmanlık tanımlanmamasının dışında, bir işlemi tanımlamaya benzer şekilde çalışır.
Örneğin:

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

veya 

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

### <a name="classical-logic-in-functions--good"></a>İşlevlerde klasik mantık = = iyi

Bunu yapmak mümkün olduğunda, işlemler içinden daha kolay bir şekilde kullanılabilmesi için klasik mantığı işlemler yerine işlevler bakımından yazmak yararlıdır.
Örneğin, `Square` bir *işlem*olarak yukarıdaki bildirimi yazdığımızda, derleyici aynı girişe çağrı yapan aynı çıktıyı tutarlı bir şekilde ürettireceğinizin garanti edilemez.

İşlevler ve işlemler arasındaki farkın altını bir şekilde çözmek için, bir Q # işlemi içinden rastgele bir sayı örnekleme sorununu ele alalım:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Her `U` çağrıldığında, üzerinde farklı bir eylem olur `target` .
Özellikle, derleyici ' a bir özelleştirme bildirimi eklediğimiz ve `adjoint auto` `U` `U(target); Adjoint U(target);` kimlik olarak (yani, işlem dışı) hareket ettiğimiz konusunda garanti edemez.
Bu, [vektörlerin ve matrislerde](xref:microsoft.quantum.concepts.vectors)gördüğdiğimiz adjoint 'in tanımını ihlal ediyor. bu nedenle, işlemi çağırdığımız bir işlemde bir adjoint özelleştirmesi otomatik olarak oluşturmaya izin veren bir işlem, <xref:microsoft.quantum.math.randomreal> derleyici tarafından verilen garantileri bozacağı, <xref:microsoft.quantum.math.randomreal> hiçbir adjoint veya kontrollü sürüm yok.

Öte yandan, bu gibi işlev çağrılarına güvenli bir şekilde izin vermek `Square` , derleyicinin `Square` çıktısının kalıcı tutulmasını sağlamak için yalnızca girişi korumasının gerektiği konusunda emin olabilir.
Bu nedenle, işlevlerde mümkün olduğunca klasik mantığı yalıtmak, diğer işlevlerde ve işlemlerde bu mantığı yeniden kullanmayı kolaylaştırır.


## <a name="generic-type-parameterized-callables"></a>Genel (tür parametreli) Callables

Tanımlamak isteyebileceğiniz birçok işlev ve işlem, kendi giriş türlerine gerçekten büyük ölçüde güvenmiyor, ancak bunun yerine yalnızca başka bir işlev veya işlem aracılığıyla türlerini örtülü olarak kullanın.
Örneğin, yaygın olarak kullanılan *harita* kavramını birçok işlevsel dilde değerlendirin. $f (x) $ işlevi ve $ \{ x_1, x_2, \noktalar, x_n $, Map bir değer koleksiyonu verildiğinde, \} $ \{ f (x_1), f (x_2), \noktalar, f (x_n) $ gibi yeni bir koleksiyon döndürür \} .
Bunu Q # ' da uygulamak için, bu işlevlerden faydalanabilir.
`Map`İhtiyaç duyduğumuz türleri öğrenirken ★ bir yer tutucu olarak kullanarak hızlı bir örnek yazalım.

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Bu işlev, yaptığımız gerçek türler dikkate alınmaz.
Örneğin, tamsayılardan Paulis 'e yapılan bir harita, kayan noktalı sayıların dizelerdeki eşlemesiyle çok benzer şekilde görünür:

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Prensibi, `Map` Karşılaşdığımız her tür çifti için bir sürümü yazalım, ancak bu çok sayıda zorluklar sunarız.
Örneğin, içinde bir hata bulduk `Map` , bu durumda düzeltilmesinin tüm sürümlerinde bir şekilde uygulandığından emin olunması gerekir `Map` .
Ayrıca, yeni bir tanımlama grubu veya UDT oluşturuyoruz, yeni tür ile birlikte yeni bir kayıt da oluşturmanız gerekir `Map` .
Bu, çok sayıda işlev için daha fazla ve daha fazla işlev topladığımızda, bu, bu tür birkaç işlevi izlüyor olsa `Map` da, yeni türleri tanıtma maliyeti oldukça kısa bir sürede makul bir şekilde büyük olur.

Bununla birlikte, bu zorluk büyük bir bölümü, derleyicinin farklı sürümlerinin nasıl ilişkili olduğunu tanıması için ihtiyaç duymadığımızda oluşur `Map` .
Etkin olarak, derleyicinin `Map` bir tür matematik işlevi olarak q # *türünden* q # işlevlerine kadar davranmamasını istiyoruz.

Bu kavram, işlevlerin ve işlemlerin *tür parametrelerine*ve bunların normal demet parametrelerine sahip olmasını sağlayarak şekillendirililir.
Yukarıdaki örneklerde, `Map` `Int, Pauli` ilk durumda ve ikinci durumda tür parametreleri varmış gibi düşünmek istiyoruz `Double, String` .
Çoğu bölüm için, bu tür parametreleri normal türlermiş gibi kullanılabilir: dizileri ve tanımlama grupları oluşturmak, işlevleri ve işlemleri çağırmak ve sıradan ya da kesilebilir değişkenlere atamak için parametre türü değerlerini kullanıyoruz.

> [!NOTE]
> Dolaylı bağımlıların en büyük olması, bir Q # programının doğrudan türün yapısına bağlı olması `Qubit` ve bu tür türleri diğer işlemlere ve işlevlere geçirmesi **gereken** qubitlerdir.

Yukarıdaki örneğe dönerek, `Map` bir tane olmak üzere bir tane olmak üzere tür parametrelerine ihtiyacım olduğunu `fn` ve çıktının temsil edilebilmesi için bir tane olduğunu görebiliriz `fn` .
Q # dilinde, bu, `<>` {} bildiriminde bir işlev veya işlemin adından sonra ve her tür parametresini listeleyerek açılı ayraçlar (brakets $ \braket $! değil) eklenerek yazılır.
Her tür parametresinin adı bir Tick ile başlamalı `'` ve sıradan bir tür ( *somut* tür olarak da bilinir) değil bir tür parametresi olduğunu gösterir.
İçin bu `Map` nedenle şunu yazıyoruz:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Tanımının, daha `Map<'Input, 'Output>` önce yazdığımız sürümlere çok benzer şekilde göründüğünü unutmayın.
Tek fark, derleyiciye doğrudan bağlı olmayan ve ne olduğunu açıkça belirttiğimiz `Map` `'Input` `'Output` , ancak bunları dolaylı olarak aracılığıyla kullanarak her iki tür için de bir bütün olarak bildirdik `fn` .
Bu şekilde tanımlandıktan sonra `Map<'Input, 'Output>` , bunu sıradan bir işlev gibi çağırabiliriz:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Genel işlevler ve işlemler yazmak, "kayıt düzeni-Out" ın Q # işlevleri ve işlemlerini düşünmek için çok faydalı bir yoldur.
> Her işlev tam olarak bir giriş yaptığından ve tam olarak bir çıkış döndürdüğünden, türünde bir giriş `'T -> 'U` *herhangi* bir Q # işleviyle eşleşir.
> Benzer şekilde, herhangi bir işlem türünde bir girişe geçirilebilir `'T => 'U` .

İkinci bir örnek olarak, iki diğer işlevin birleşimini döndüren bir işlev yazma sınamasını göz önünde bulundurun:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Burada, tam olarak ne, ve ne olduğunu belirtmemiz gerekir `A` `B` `C` . bu nedenle, yeni işlevimizin yardımcı programını ciddi ölçüde kısıtlar `Compose` .
All,,, ve ile `Compose` bağlıdır `A` `B` `C` *via* `innerFn` `outerFn` .
Alternatif olarak,,, `Compose` ve için çalıştığını belirten tür parametreleri ekleyebiliriz *any* `A` `B` `C` ve bu parametrelerin, ve ile beklenen olanlarla eşleştiği sürece `innerFn` `outerFn` :

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Q # standart kitaplıkları, daha yüksek sıralı denetim akışı hızlı bir şekilde daha kolay hale getirmek için tür parametreli işlem ve işlev aralığı sağlar.
Bunlar, [Q # standart kitaplığı kılavuzunda](xref:microsoft.quantum.libraries.standard.intro)daha ayrıntılı olarak ele alınmıştır.


## <a name="callables-as-first-class-values"></a>Ilk sınıf değerleri olarak callables

İşlemler yerine işlevleri kullanarak denetim akışı ve klasik mantık hakkında önemli bir tekniktir, bu işlemler ve Q # içindeki işlevler *birinci sınıf*olur.
Diğer bir deyişle, her bir değer kendi sağ tarafındaki dilde değerlerdir.
Örneğin, daha az dolaylı bir değer varsa, aşağıdakiler mükemmel bir Q # kodudur:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

`ourH`Yukarıdaki kod parçacığında değişkenin değeri, daha sonra <xref:microsoft.quantum.intrinsic.h> Bu değeri başka bir işlem gibi çağırabilmemiz için işlem olur.
Bu, daha yüksek sıralı denetim akışı kavramlarını oluşturan, işlemleri girişin bir parçası olarak alan işlemleri yazmamızı sağlar.
Örneğin, aynı hedef qubit 'e iki kez uygulanarak bir işlemi "kare" olarak ele geçirebilir.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>İşlevden işlem döndürme

İşlemler, bir işlem biçiminde bir hisse programın açıklamasını döndüren klasik bir işlev olarak bazı klasik koşullu mantığı ayırabilmemiz gibi, işlemleri çıktıların bir parçası olarak de döndürebiliyoruz.
Basit bir örnek olarak, iki bitlik bir klasik ileti alan tarafın, bu iletiyi kullanarak doğru bir teleporm durumuna ulaşmasını sağlamak için ileti kullanması gereken teleporsyon örneğini düşünün.
Bunu, bu iki klasik biti alan ve uygun kod çözme işlemini döndüren bir işlev açısından yazalım.

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

Bu yeni işlev aslında bir işlevdir, ancak aynı ve değerlerini aynı şekilde çağırırsanız `hereBit` `thereBit` , her zaman aynı işlemi geri alacaksınız.
Bu nedenle, kod çözme mantığının farklı işlem özelleştirmelerinin tanımlarıyla nasıl etkileşime gireceğini öğrenmek zorunda kalmadan güvenli şekilde işlemler içinde çalıştırılabilir.
Diğer bir deyişle, bir işlev içinde klasik mantığı yalıtdık ve bu, bir derleyicinin işlev çağrısının Impunity ile yeniden düzenlenmesine ve girişin korunduğu sürece bir şekilde yeniden sıralanacağını kabul ettik.


## <a name="partial-application"></a>Kısmi uygulama

*Kısmi uygulama*kullanarak işlem döndüren işlevlerle çok daha fazlasını yapabiliriz, burada, girişin bir veya daha fazla bölümünü bir işleve veya işleme bir veya daha fazla şekilde aramadan sağlayabiliriz. Örneğin, yukarıdaki örneği geri çektireceğiz, `ApplyTwice` giriş işleminin hangi qubit 'e uygulanacağını, doğru bir şekilde belirtmek istediğimiz olduğunu belirtebiliriz:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

Bu durumda, yerel değişken `twiceOp` kısmen uygulanan işlemi tutar `ApplyTwice(op, _)` ; burada, girişin henüz belirtilmemiş olduğu parçalar tarafından gösterilir `_` .
Aslında bir sonraki satırda arama yaptığımız zaman `twiceOp` , girişin kalan tüm bölümlerinin özgün işleme göre kısmen uygulanmış işleme giriş olarak geçeceğiz.
Bu nedenle, yukarıdaki kod parçacığı, `ApplyTwice(op, target)` doğrudan çağrılmasıyla daha da benzer bir şekilde, girişin bazı parçalarını sağlarken çağrıyı gecikmemizi sağlayan yeni bir yerel değişken sunuyoruz.

Kısmen uygulanmış bir işlem, tüm giriş sağlanana kadar gerçekten çağrılmadığı için, işlevleri içinden bile işlemleri güvenle uygulayabilirsiniz.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

Prensibi, içindeki klasik mantık çok `SquareOperation` daha fazla olabilir, ancak derleyicinin işlevler hakkında sunabileceği garantilere göre bir işlemin geri kalanından yalıtılmıştır.
Bu yaklaşım, klasik denetim akışını hisse uygun şekilde kullanılmak üzere bir şekilde ifade etmek için Q # standart kitaplığı genelinde kullanılacaktır.


## <a name="recursion"></a>Özyineleme

Q # callables 'in doğrudan veya dolaylı olarak özyinelemeli olmasına izin verilir.
Diğer bir deyişle, bir işlem veya işlev kendisini çağırabilir veya çağrılabilir işlemi doğrudan veya dolaylı olarak çağıran başka bir çağrılabilir çağrısı sağlayabilir.

Ancak özyineleme kullanımı hakkında iki önemli yorum vardır:

- İşlemlerde özyineleme kullanımı, bazı iyileştirmelere engel olabilir.
  Bu, algoritmanın yürütme süresi üzerinde önemli bir etkiye sahip olabilir.
- Gerçek bir hisse cihazında yürütme yaparken, yığın alanı sınırlı olabilir ve bu nedenle derin özyineleme bir çalışma zamanı hatasına neden olabilir.
  Özellikle, Q # derleyicisi ve çalışma zamanı, kuyruk özyinelemeyi tanımlamaz ve iyileştirmez.

## <a name="whats-next"></a>Sırada Ne Var?
Q # [değişkenleri](xref:microsoft.quantum.guide.variables) hakkında bilgi edinin.