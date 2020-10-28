---
title: İçindeki işlemler ve işlevler Q#
description: İşlem ve işlevlerin yanı sıra denetlenen ve Adjoint işlem uzmanlıklarını tanımlama ve çağırma.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
no-loc:
- Q#
- $$v
ms.openlocfilehash: 55e6d3e1a242386c46213083692377520df83a80
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692143"
---
# <a name="operations-and-functions-in-no-locq"></a>İçindeki işlemler ve Işlevler Q#

## <a name="defining-new-operations"></a>Yeni Işlemleri tanımlama

İşlemleri Core Q# .
Bildirdikten sonra, klasik .NET uygulamalarından çağrılabilir, örneğin, simülatör veya içinde başka işlemler olabilir Q# .
İçinde tanımlanan her işlem Q# , dil tarafından tanımlanan yerleşik iç işlemler de dahil olmak üzere herhangi bir sayıda işlemi çağırabilir. Q#Bu iç işlemleri tanımlayan belirli bir yol, hedef makineye bağlıdır.
Derlendiğinde, her işlem hedef makinelere sağlanlenebilecek bir .NET sınıf türü olarak temsil edilir.

Her Q# kaynak dosya, herhangi bir sayıda işlem tanımlayabilir.
İşlem adları ad alanı içinde benzersiz olmalıdır ve tür veya işlev adlarıyla çakışmayabilir.

İşlem bildirimi, anahtar sözcüğünden ve `operation` ardından işlemin adı olan sembol, işlem için bağımsız değişkenleri tanımlayan türü belirlenmiş bir tanımlayıcı tanımlama grubu, iki nokta üst üste `:` , işlemin sonuç türünü açıklayan bir tür açıklaması, isteğe bağlı olarak işlem özellikleri olan bir ek açıklama, bir açık küme ayracı ve sonra da işlem bildiriminin gövdesini içerir `{ }` .

Her işlem bir girdi alır, bir çıktı üretir ve bir veya daha fazla işlem uzmanlığını için uygulamayı belirtir.
Olası Uzmanlıklar ve bunların nasıl tanımlanacağı ve çağrılacağını, bu makalenin farklı bölümlerinde ayrıntılı olarak açıklanmıştır.
Şimdilik yalnızca bir varsayılan gövde özelleştirmesi tanımlayan ve giriş olarak tek bir qubit alan aşağıdaki işlemi göz önünde bulundurun ve sonra <xref:Microsoft.Quantum.Intrinsic.X> Bu girişte yerleşik işlemi çağırır:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

Anahtar sözcüğü, `operation` işlem tanımını ve ardından adı ile başlar; burada, `BitFlip` .
Sonra, giriş türü, `Qubit` `target` Yeni işlemdeki girişe başvurmak için bir adla birlikte tanımlanır ().
Son olarak, `Unit` işlemin çıktısının boş olduğunu tanımlar.
`Unit` , `void` C# ve diğer zorunlu dillerde aynı şekilde kullanılır ve `unit` F # ve diğer işlevsel dillerde eşdeğerdir.

İşlemler Ayrıca, öğesinden daha ilginç türler de döndürebilir `Unit` .
Örneğin, işlem, <xref:Microsoft.Quantum.Intrinsic.m> `Result` ölçüm gerçekleştirmemiş olduğunu temsil eden türünde bir çıktı döndürür.  Bir işlemden başka bir işleme geçirebilirsiniz veya `let` Yeni bir değişken tanımlamak için anahtar sözcükle birlikte kullanabilirsiniz.

Bu yaklaşım, en [yoğun kodlama](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding)gibi düşük bir düzeyde hisse uygun olan klasik hesaplamayı temsil etmenizi sağlar:

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
> İçindeki her işlem Q# tam olarak bir giriş alır ve tam olarak bir çıkış döndürür.
> Birden çok giriş ve çıkış, birden çok değeri birlikte tek bir değerde depolayan *Tanımlama grupları* kullanılarak temsil edilir.
> Bu şekilde, Q# "kayıt düzeni oluşturma" dilidir.
> Bu kavramı takip eden bir dizi boş parantezler, `()` daha sonra türü olan "boş" kayıt düzeni olarak okunmalıdır `Unit` .

## <a name="controlled-and-adjoint-operations"></a>Denetlenen ve Adjoint Işlemleri

Bir işlem, içindeki birçok işlem için olduğu gibi bir Unitary dönüştürmesi uygularsa, Q# *adjointed* veya *denetimli* olduğunda işlemin nasıl davrandığını tanımlamak mümkündür. Bir işlemin *adjoint* özelleştirmesi işlemin nasıl davranması gerektiğini belirtir, *denetimli* bir özelleşme, uygulamanın belirli bir hisse kaydı durumunda olduğu durumlarda bir işlemin nasıl davranması gerektiğini belirtir.

Hisse unsurlarının bir bölümünü, hisse bilgi işlem işlemlerinin birçok yönü için çok önemlidir. Faydalı programlama tekniğinin yanı sıra ele alınan bir durumla ilgili bir örnek için Q# bkz. [Denetim akışı: conjugations](xref:microsoft.quantum.guide.controlflow#conjugations). Bir işlemin denetlenen sürümü, yalnızca tüm denetim qubits 'in belirtilen durumda olması durumunda temel işlemi etkili bir şekilde uygulayan yeni bir işlemdir.
Denetim qubitleri üst konumundayken, temel işlem üst konumun uygun bölümüne doğru şekilde uygulanır.
Bu nedenle, denetimli işlemler genellikle entanglement oluşturmak için kullanılır.

Doğal olarak, *denetlenen bir adjoint* özelleştirmesi de bir işlemin adjoint öğesinin denetimli uygulamasını belirterek bulunabilir.

> [!NOTE]
> $U $, bir işlem tarafından uygulanan Unitary dönüşümünde `U` , `Adjoint U` karmaşık eşleniği devrik olan "^ \dağılım $ $U Unitary dönüşümünü temsil eder.
> Bir işlemin büyük bir bir şekilde uygulanması ve sonra adekliği, bu durum, $UU ^ \gger = U ^ \gger U = \ID $, kimlik matrisi olan olgu tarafından gösterildiği gibi durumu değişmeden bırakır.
> Denetlenen bir işlemin Unitary temsili biraz daha fazla bir işlemdir, ancak daha fazla ayrıntı için [hisse bilgi işlem kavramlarıyla daha fazla bilgi bulabilirsiniz: birden çok qubit](xref:microsoft.quantum.concepts.multiple-qubits).

Aşağıdaki bölümde, bu çeşitli uzmanların kodunuzda nasıl çağrılacağını Q# ve bunları desteklemek için işlemlerin nasıl tanımlanacağı açıklanmaktadır.

### <a name="calling-operation-specializations"></a>İşlem uzmanlık işlemleri çağrılıyor

' De bir *functor* Q# , başka bir işlemden yeni bir işlem tanımlayan bir fabrikadır.
İçindeki iki standart komik, Q# ve ' `Adjoint` dir `Controlled` .

Funörler, yeni işlemin uygulamasını tanımlarken temel işlemin uygulamasına erişebilir.
Bu nedenle, funörler geleneksel daha yüksek düzey işlevlerden daha karmaşık işlevler gerçekleştirebilir. Funörler tür sisteminde bir gösterimine sahip değildir Q# . Bu nedenle, şu anda bunları bir değişkene bağlamak veya bağımsız değişken olarak geçirmek mümkün değildir. 

Yeni bir işlem döndüren bir işleme uygulayarak bir functor kullanın.
Örneğin, `Adjoint` işlem için functor uygulandığında `Y` Yeni işlem döndürülür `Adjoint Y` . Yeni işlemi başka bir işlem gibi çağırabilirsiniz.
Bir işlemin veya komik uygulamalarının uygulamasını desteklemesi için `Adjoint` `Controlled` dönüş türünün olması gerekir `Unit` . 

#### <a name="adjoint-functor"></a>`Adjoint` functor

Bu nedenle, `Adjoint Y(q1)` `Adjoint` `Y` Yeni bir işlem oluşturmak için functor işlemini uygular ve bu yeni işlemi öğesine uygular `q1` .
Yeni işlem, temel işlemle aynı imzaya ve türe sahip `Y` .
Özellikle, yeni işlem de destekler `Adjoint` ve `Controlled` yalnızca temel işlem olduysa, ve desteklenir.
`Adjoint`Functor kendi tersidir; diğer bir deyişle, `Adjoint Adjoint Op` her zaman ile aynıdır `Op` .

#### <a name="controlled-functor"></a>`Controlled` functor

Benzer şekilde, `Controlled X(controls, target)` `Controlled` `X` Yeni bir işlem oluşturmak için functor işlemini uygular ve bu yeni işlemi ve için uygular `controls` `target` .

> [!NOTE]
> Q#' De, denetimli sürümler her zaman bir denetim qubit dizisini alır ve denetim her zaman hesaplama ( `PauliZ` ) durumunda olan `One` $ \tus$ olan tüm denetim qubits 'i temel alır {1} .
> Diğer durumlara göre denetlemek, denetimli işlemden önce denetim qubits 'e uygun Unitary işlemini uygulayarak ve sonra, denetimli işlemden sonra Unitary işleminin evirimini uygulayarak elde edilir.
> Örneğin, `X` denetimli bir işlemden önce ve sonra bir işlemi bir denetim qubit uygulamak, `Zero` Bu qubit için ($ \ket $) durumunda işlemin denetlenmesini sağlar {0} ; durum `H` üzerinde ve sonrasında denetimleri `PauliX` `One` , durum yerine Pauli X, $ \tus\mathrel{ {-} : =} (\tus- {0} {1} \tus)/\sqrt {2} $ olan `PauliZ` `One` -1.

Bir işlem ifadesi verildiğinde, functor kullanarak yeni bir işlem ifadesi oluşturabilirsiniz `Controlled` .
Yeni işlemin imzası, özgün işlemin imzasını temel alır.
Sonuç türü aynıdır, ancak giriş türü, ilk öğe olarak denetim qubit dizisini ve ikinci öğe olarak orijinal işlemin bağımsız değişkenlerini tutan bir qubit dizisi olan iki kayıt türüdür.
Yeni işlem `Controlled` ' i destekler ve `Adjoint` yalnızca özgün işlem olduysa, ve yalnızca bunu destekler.

Özgün işlem yalnızca tek bir bağımsız değişken alıyorsa, tek [demet denklik](xref:microsoft.quantum.guide.types) , burada oynat olarak gelir.
Örneğin, `Controlled X` işlemin denetlenen sürümüdür `X` . 
`X` türüne sahip `(Qubit => Unit is Adj + Ctl)` , `Controlled X` Bu nedenle türüne sahip `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` . tek kayıt düzeni denkliği nedeniyle bu, ile aynıdır `((Qubit[], Qubit) => Unit is Adj + Ctl)` .

Temel işlem birkaç bağımsız değişken alıyorsa, bu işlemin denetlenen sürümünün ilgili bağımsız değişkenlerini, bir tanımlama grubu içine dönüştürmek için parantez içine almayı unutmayın.
Örneğin, `Controlled Rz` işlemin denetlenen sürümüdür `Rz` . 
`Rz` türüne sahip `((Double, Qubit) => Unit is Adj + Ctl)` , bu nedenle `Controlled Rz` türüne sahip `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .
Bu nedenle, `Controlled Rz(controls, (0.1, target))` geçerli bir çağrısı olur `Controlled Rz` (etrafındaki ayraçları aklınızda bulunan `0.1, target` ).

Başka bir örnek olarak, `CNOT(control, target)` olarak uygulanabilir `Controlled X([control], target)` . Bir hedefin iki denetim qubits (CCNOT) tarafından denetlenmesi gerekiyorsa, bir `Controlled X([control1, control2], target)` ifade kullanın.

#### `Controlled Adjoint` 

`Controlled`Ve `Adjoint` komik, ve uygulama arasında bir fark yoktur `Controlled Adjoint Op` `Adjoint Controlled Op` .


## <a name="defining-controlled-and-adjoint-implementations"></a>Denetlenen ve Adjoint uygulamalarını tanımlama

Önceki örneklerde ilk işlem bildiriminde, işlemler `BitFlip` ve `DecodeSuperdense` sırasıyla imzalar ve ile tanımlanmıştır `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` .
`DecodeSuperdense`Ölçümler de dahil olmak üzere, Unitary bir işlem değildir ve bu nedenle hiçbir adeksel uzmanlık yok (Bu, bu tür bir işlemin döndürdüğü ilgili gereksinimi geri çağırır `Unit` ).
Ancak, `BitFlip` yalnızca Unitary işlemini gerçekleştirdiğinden, <xref:Microsoft.Quantum.Intrinsic.X> bunu her iki uzmanlıklarla tanımlamış olabilirsiniz.

Bu bölümde, işlem bildirimlerinizde uzmanlıklarınızın nasıl dahil olduğu Q# , bu nedenle veya komik bir şekilde çağrılabilir `Adjoint` `Controlled` .
Bazı durumlar hakkında daha fazla bilgi edinmek için geçerli olduğu veya bazı Uzmanlıkları bildirmek için geçerli olmayan durumlar hakkında daha fazla bilgi için, bu makaledeki [özelleştirilmiş oluşturmaları Ilgili koşullar](#circumstances-for-validly-defining-specializations) bölümüne bakın.

İşlem özellikleri, bildirildiği işleme ne tür işlevler uygulayabileceğinizi ve sahip oldukları etkiyi tanımlar. Bu uzmanlıklardan biri, özellikle işlem özelliklerine sahip bir ek açıklama aracılığıyla işlem imzasının bir parçası olarak bildirilemez: `is Adj` ,, `is Ctl` veya `is Adj + Ctl` .
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
Bu nedenle, `DecodeSuperdense` `PrepareEntangledPair` entangled durumunu bir qubit çiftiyle geri dönüştürmek için adjoint öğesini kullanarak önceki örneğe daha fazla sıkı yazmak için bunu kullanabilirsiniz:

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

Bildirimin işlem özellikleriyle birlikte ek açıklama, derleyicinin varsayılan uygulamaya göre diğer özelleştirmeleri otomatik olarak üretmesinin güvence altına almak için yararlıdır. 

Funlar ile kullanım için işlemleri tasarlarken göz önünde bulundurmanız gereken birkaç önemli sınırlama vardır.
Aynı etkiyi elde etmek için bu tür bir işlemde deyimleri yeniden sıralamak belirsiz olduğundan, başka bir *işlemin çıkış* değerini kullanan bir işlem için en kritik öneme sahip olan uzmanlık, derleyici tarafından otomatik olarak üretilemez.

Bu nedenle, genellikle çeşitli uygulamaları açıkça belirtmek yararlı olur.

### <a name="explicitly-specifying-implementations"></a>Uygulamaları açıkça belirtme

Derleyicinin uygulamayı oluşturabileceği durumda, bunu açıkça belirtebilirsiniz. Bu tür açık özelleşmeler, uygun bir *oluşturma yönergesinin* veya Kullanıcı tanımlı bir uygulamadan oluşabilir.
Aşağıda, bazı açık özelleşmeye örnek olarak tüm olasılıklar verilmiştir. 


#### <a name="explicit-specialization-declarations"></a>Açık Özelleştirme bildirimleri

Q# işlemler aşağıdaki açık özelleştirme bildirimlerini içerebilir:

- `body`Özelleşme, hiçbir komik uygulanmamış şekilde işlemin uygulanmasını belirtir.
- `adjoint`Özelleşme, işlem için `Adjoint` functor uygulanmış olan uygulamayı belirtir.
- `controlled`Özelleşme, işlem için `Controlled` functor uygulanmış olan uygulamayı belirtir.
- `controlled adjoint`Özelleşme, hem hem de `Adjoint` funları uygulanan işlemin uygulanmasını belirtir `Controlled` .
  Bu özelleşme `adjoint controlled` , iki komik bulunduğu için de adlandırılmış olabilir.


Bir işlem özelleştirmesi, özelleştirme etiketinden oluşur (örneğin, `body` veya) ve `adjoint` aşağıdakilerden biri:

- Aşağıda açıklandığı gibi açık bir bildirim.
- Derleyiciye özelleştirmenin *nasıl* oluşturulacağını belirten bir *yönerge* , aşağıdakilerden biri:
  - `intrinsic`, hedef makinenin özelleşme sağladığını gösterir.
  - `distribute`, `controlled` ve `controlled adjoint` uzmanlıklarıyla kullanılır.
    İle kullanıldığında `controlled` , derleyicinin `Controlled` , içindeki tüm işlemlere uygulanarak özelleştirmeyi hesaplaması gerektiğini belirtir `body` .
    İle kullanıldığında `controlled adjoint` , derleyicinin özelleşmenin tüm işlemlerine uygulayarak özelleştirmeyi hesaplaması gerektiğini belirtir `Controlled` `adjoint` .
  - `invert`, `adjoint` `body` Örneğin, örneğin, işlem sırasını ters çevirerek ve adeki her birine uygulayarak, derleyicinin özelleştirmeyi hesaplaması gerektiğini gösterir.
    İle kullanıldığında `adjoint controlled` , bu, derleyicinin özelleştirmeyi ters çeviren şekilde özelleşmesi gerektiğini belirtir `controlled` .
  - `self`, adjoint özelleşmenin özelleştirme ile aynı olduğunu göstermek için `body` .
    Kullanımı `self` ve uzmanlık için geçerlidir `adjoint` `adjoint controlled` .
    İçin `adjoint controlled` , `self` `adjoint controlled` özelleştirmenin özelleştirme ile aynı olduğunu gösterir `controlled` .
  - `auto`, derleyicinin uygulanacak uygun bir yönergeyi seçmesini belirtmek için.
    `auto`Özelleştirme için kullanamazsınız `body` .

Yönergelerin ve `auto` tümünün bir kapanış noktalı virgül olması gerekir `;` .
`auto`Bir açık bildirimi sağlanmışsa, yönergesi aşağıdaki oluşturulan yönergeyi çözümler `body` :

- `adjoint`Özelleşme, yönergeye göre oluşturulur `invert` .
- `controlled`Özelleşme, yönergeye göre oluşturulur `distribute` .
- `adjoint controlled` `invert` İçin açık bir bildirime izin `controlled` verildiğinde ve yoksa, özelleştirme yönergeye göre oluşturulur `adjoint` `distribute` .

> [!TIP]   
> Bir işlem kendi kendine adekiyiyise, `self` derleyicinin en iyi duruma getirme amacıyla bu bilgileri kullanmasına izin vermek için oluşturma yönergesi aracılığıyla adjoint veya denetimli adjoint özelleşmesini açıkça belirtin.

Kullanıcı tanımlı bir uygulama içeren bir özelleştirme bildirimi, bir bağımsız değişken kayıt kümesinden ve ardından özelleşmeyi uygulayan kodla bir ifade bloğunun yer aldığı bir Q# .
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

Önceki `PrepareEntangledPair` örnekte, kod açık özelleştirme bildirimlerini içeren aşağıdaki koda eşdeğerdir: 

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

Derleyici belirli bir özelleşmenin uygulamasını otomatik olarak üretemiyor veya daha verimli bir uygulama verilirse, uygulamayı el ile tanımlayabilirsiniz.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
Önceki örnekte, `adjoint invert;` adjoint özelleşmesinin, gövde uygulamasını tersine çeviren ve denetlenen `controlled adjoint invert;` majoint özelleşmesinin, denetlenen özelleşmenin belirtilen uygulamasını tersine ayırarak oluşturulacağını belirtir.

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

Adjoint veya denetimli sürümleri olmayan bir işlem belirtmek için geçerlidir. Örneğin, ölçüm işlemleri tersine çevrilebilir veya denetlenebilir olmadıkları için içermez.

Bir işlem, `Adjoint` `Controlled` bildirimi ilgili özelleştirmeler için örtük veya açık bir bildirim içeriyorsa, ve funları destekler.

Açıkça tanımlanmış bir adjoint/kontrollü özelleştirme, bir adjoint/denetimli özelleştirmenin varlığını gösterir. 

Gövdesi, yineleme-Until-başarılı döngüleri, set deyimlerini, ölçümleri, return deyimlerini veya funı desteklemeyen diğer işlemlere yapılan çağrıları içeren bir işlem için, `Adjoint` veya yönergesini izleyen bir adjoint özelleşmenin otomatik olarak oluşturulması `invert` `auto` mümkün değildir.

Gövdesi, functor desteklemeyen diğer işlemlere çağrı içeren bir işlem için `Controlled` , veya yönergesini izleyen denetimli bir özelleşmenin otomatik olarak oluşturulması `distribute` `auto` mümkün değildir.

#### <a name="controlled-adjoint"></a>Kontrollü adjoint

Bir işlemin kontrollü adjoint sürümü, işlemin adjoint öğesinin hisse kontrollü bir sürümünün nasıl uygulanacağını belirtir.
Denetlenen adjoint sürümü olmayan bir işlem belirtmek için geçerlidir; Örneğin, ölçüm işlemlerinde denetlenebilir veya ters çevrilebilir olmadıkları için denetimli bir adjoint sürümü yoktur.

Bir işlem için denetimli bir adjoint özelleştirmesi, ve yalnızca bir adjoint ve denetimli bir özelleştirme varsa var olmalıdır. Bu durumda, denetlenen adjoint özelleşmenin varlığı algılanır. Açıkça tanımlanmış bir uygulama yoksa, derleme uygun bir özelleştirme oluşturur.

Gövdesi denetimli bir adjoint sürümüne sahip olmayan diğer işlemlere çağrı içeren bir işlem için,, veya yönergesini izleyen bir adjoint özelleşmenin otomatik olarak oluşturulması `invert` `distribute` `auto` mümkün değildir.


### <a name="type-compatibility"></a>Tür uyumluluğu

Daha az komik, ancak aynı imzaya sahip bir işlem kullandığınızda her yerde desteklenen ek komik bir işlem kullanın. Örneğin, türündeki bir işlemi kullandığınız her yerde türünde bir işlem kullanın `(Qubit => Unit is Adj)` `(Qubit => Unit)` .

Q# çağrılabilir dönüş türlerine göre *birlikte değişken* : bir tür döndüren çağrılabilir, `'A` aynı giriş türüne ve ile uyumlu bir sonuç türüne sahip çağrılabilir ile uyumludur `'A` .

Q# , giriş türlerine göre *değişken karşıtı:* giriş olarak bir türü alan çağrılabilir, `'A` aynı sonuç türü ve ile uyumlu bir giriş türü olan çağrılabilir ile uyumludur `'A` .

Diğer bir deyişle, aşağıdaki tanımlar verildiğinde,

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

Şunları yapabilirsiniz

- `ConjugateInvertWith` `inner` Ya da bağımsız değişkeniyle işlevi çağırın `Invert` `ApplyUnitary` .
- İşlevi `ConjugateUnitaryWith` bir `inner` bağımsız değişkeniyle çağırın `ApplyUnitary` , ancak not edin `Invert` .
- Türünden bir değer döndürür `(Qubit[] => Unit is Adj + Ctl)` `ConjugateInvertWith` .

> [!IMPORTANT]
> Q# 0,3, Kullanıcı tanımlı türlerin davranışında önemli bir farklılık sunmuştur.

Kullanıcı tanımlı türler, alt tür yerine temel alınan türün Sarmalanan bir sürümü olarak değerlendirilir.
Bu, Kullanıcı tanımlı türün bir değerinin, temel alınan türün bir değerini beklediğinizi tahmin ettiğiniz durumlarda kullanılabilir olmadığı anlamına gelir.


## <a name="defining-new-functions"></a>Yeni Işlevleri tanımlama

İşlevler, ' de, Q# bir çıkış değeri hesaplamasının ötesinde etkileri olmasına izin verilmediğinden işlemlerinden farklı olarak, ' de yalnızca belirleyici ve klasik yordamlardır.
Özellikle, işlevler işlemleri çağıramaz; işlem yapın, ayırın veya ödünç alma; örnek rastgele sayılar; ya da diğer bir deyişle, giriş değerinin ötesine bir işleve bağımlı duruma bağlıdır.
Sonuç olarak, Q# işlevler *saf* olduğundan, her zaman aynı giriş değerlerini aynı çıkış değerleriyle eşleştirirler.
Bu davranış, Q# derleyicinin işlem uzmanlıklarını oluştururken işlevlerin nasıl ve ne zaman çağrılacağını güvenle yeniden oluşturmasını sağlar.

Her Q# kaynak dosya, herhangi bir sayıda işlev tanımlayabilir.
İşlev adları bir ad alanı içinde benzersiz olmalıdır ve işlem veya tür adlarıyla çakışamaz.

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

Bunu yapmak mümkün olduğunda, işlemleri daha kolay kullanabilmek için işlemler yerine işlevler bakımından klasik mantığı yazmak yararlı olur. Örneğin, önceki `Square` bildirimi bir *işlem* olarak yazdıysanız, derleyici aynı girişe çağrı yapan aynı çıkışları tutarlı bir şekilde üretmesi gerektiğini garanti edemeyebilir.

İşlevler ve işlemler arasındaki farkı altı çizili yapmak için, bir işlemin içinden rastgele bir sayı örnekleme sorununu ele alalım Q# :

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

Her `U` çağrıldığında, üzerinde farklı bir eylem vardır `target` .
Özellikle, derleyici ' `adjoint auto` a bir özelleştirme bildirimi eklerseniz `U` , `U(target); Adjoint U(target);` kimlik olarak davranır (yani, işlem dışı).
Bu durum, [vektörlerin ve matrislerde](xref:microsoft.quantum.concepts.vectors)tanımlanan adekin tanımını ihlal eder, bu nedenle derleyicinin, işlemi çağırdığınız bir işlemde bir adjoint özelleşmesinin otomatik olarak oluşturmasını sağlayan bir işlem, <xref:Microsoft.Quantum.Math.RandomReal> derleyici tarafından sağlanmaları kesintiye uğratır; <xref:Microsoft.Quantum.Math.RandomReal> hiçbir adjoint veya kontrollü sürüm yok.

Öte yandan, gibi işlev çağrılarına izin verme `Square` ve derleyicinin `Square` çıktısının kalıcı kalmasını sağlamak için yalnızca girdiyi korumasının gerektiği konusunda bir değer sağlar.
Bu nedenle, işlevlerde mümkün olduğunca klasik mantığı yalıtmak, diğer işlevlerde ve işlemlerde bu mantığı yeniden kullanmayı kolaylaştırır.


## <a name="generic-type-parameterized-callables"></a>Genel (tür parametreli) Callables

Tanımlamak isteyebileceğiniz birçok işlev ve işlem, kendi giriş türlerine gerçekten büyük ölçüde güvenmiyor, ancak bunun yerine yalnızca başka bir işlev veya işlem aracılığıyla türlerini örtülü olarak kullanın.
Örneğin, yaygın olarak kullanılan *harita* kavramını birçok işlevsel dilde değerlendirin. $f (x) $ işlevi ve $ \{ x_1, x_2, \noktalar, x_n $, Map bir değer koleksiyonu verildiğinde, \} $ \{ f (x_1), f (x_2), \noktalar, f (x_n) $ gibi yeni bir koleksiyon döndürür \} .
Bunu uygulamak için Q# , işlevlerin ilk sınıf olduğu olgunun avantajlarından yararlanın.
İşte `Map` , `T` ihtiyacınız olan türleri öğrenirken yer tutucu olarak kullanmanın hızlı bir örneği.

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Bu işlevin, hangi gerçek türleri Beğendiğinize bakılmaksızın çok fazla göründüğünü unutmayın.
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

İlke ' de, `Map` karşılaştığınız her tür çifti için bir sürümü yazabilirsiniz, ancak bu çok sayıda zorluklar ortaya koymaktadır.
Örneğin, içinde bir hata bulursanız `Map` , düzeltmesinin tüm sürümlerinde bir şekilde uygulandığından emin olmanız gerekir `Map` .
Ayrıca, yeni bir tanımlama grubu veya UDT oluşturursanız, yeni türle birlikte yeni bir kayıt da oluşturmanız gerekir `Map` .
Bu, az sayıda işlev için daha fazla ve daha fazla işlev topladıkça, bu tür bir izleme tablosu olsa da `Map` , yeni türleri tanıtma maliyeti oldukça kısa bir süre boyunca makul bir şekilde büyük olur.

Bununla birlikte, bu zorluklar, derleyicinin farklı sürümlerinin nasıl ilişkili olduğunu tanıması için ihtiyaç duymamanızdan kaynaklanır `Map` .
Etkin olarak, derleyicinin `Map` türlerden bir tür matematik işlevi olarak bir tür işlevi görmesini istersiniz Q# *types* Q# .

Q# işlevlerin ve işlemlerin *tür parametrelerine* ve sıradan demet parametrelerine izin vererek bu kavramı şekillendirir.
Önceki örneklerde, `Map` `Int, Pauli` ilk durumda ve ikinci durumda tür parametrelerine sahip olacak şekilde düşünmek istersiniz `Double, String` .
Çoğu bölüm için, bu tür parametrelerini sıradan türlermiş gibi kullanın. Dizi ve tanımlama oluşturmak, işlevleri ve işlemleri çağırmak ve sıradan ya da kesilebilir değişkenlere atamak için parametre türü değerlerini kullanın.

> [!NOTE]
> Dolaylı bağımlıların en büyük olması, bir Q# programın doğrudan türün yapısına bağlı olması, `Qubit` ancak bu tür türleri diğer işlemlere ve işlevlere geçirmesi **gereken** qubitlerdir.

Önceki örneğe dönerek, `Map` bir tane olmak üzere tür parametrelerine sahip olması gerektiğini, diğeri girişi temsil etmek için `fn` ise çıktıyı temsil edecek şekilde görürsünüz `fn` .
İçinde Q# , bu, `<>` {} bildiriminde bir işlev veya işlemin adından sonra ve her tür parametresini listeleyerek açılı ayraç (yani brakets $ \bratus$! değil) eklenerek yazılır.
Her tür parametresinin adı bir Tick ile başlamalı `'` ve sıradan bir tür ( *somut* tür olarak da bilinir) değil bir tür parametresi olduğunu gösterir.
Bu nedenle, `Map` yazılır:

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

Tanımının `Map<'Input, 'Output>` previoius sürümlerine çok benzer şekilde göründüğünü unutmayın.
Tek fark, derleyiciye doğrudan bağlı olmayan ve ne olduğunu açıkça bildirdiğinize `Map` `'Input` `'Output` , ancak bunları dolaylı olarak aracılığıyla kullanarak her iki tür için de işe yarar `fn` .
Bu şekilde tanımladıktan sonra `Map<'Input, 'Output>` , normal bir fonksiyonmuş gibi çağırabilirsiniz:

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> Genel işlevler ve işlemler yazmak, "demet oluşturma-kapatma" Q# işlevinin işlevler ve işlemler hakkında düşünmek için çok faydalı bir yoldur.
> Her işlev tam olarak bir giriş yaptığından ve tam olarak bir çıkış döndürdüğünden, tür girişi `'T -> 'U` herhangi bir *any* Q# işlevle eşleşir.
> Benzer şekilde, herhangi bir işlemi türü bir girişe geçirebilirsiniz `'T => 'U` .

İkinci bir örnek olarak, iki diğer işlevin birleşimini döndüren bir işlev yazma sınamasını göz önünde bulundurun:

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Burada, tam olarak ne `A` , `B` ve olduğunu belirtmeniz gerekir `C` . bu nedenle, yeni işlevimizin yardımcı programını ciddi ölçüde sınırlandırırsınız `Compose` .
All,,, ve ile `Compose` bağlıdır `A` `B` `C` *via* `innerFn` `outerFn` .
Alternatif olarak,,, `Compose` ve için çalıştığını göstermek üzere tür parametreleri ekleyebilirsiniz *any* `A` `B` `C` ve bu parametrelerin, ve tarafından beklenenlerle eşleştiği sürece `innerFn` `outerFn` :

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Q#Standart kitaplıklar, daha yüksek sıralı denetim akışını Express 'in daha kolay hale getirmek için bu tür parametreli işlemler ve işlevlerin bir aralığını sunar.
Bunlar, [ Q# standart kitaplık kılavuzunda](xref:microsoft.quantum.libraries.standard.intro)daha ayrıntılı olarak ele alınmıştır.


## <a name="callables-as-first-class-values"></a>First-Class değerler olarak callables

İşlemler yerine işlevleri kullanarak denetim akışı ve klasik mantık hakkında önemli bir tekniktir, bu işlemleri ve işlevleri Q# *ilk sınıfındır* .
Diğer bir deyişle, her bir değer kendi sağ tarafındaki dilde değerlerdir.
Örneğin, daha az dolaylı bir değer varsa, aşağıdakiler tam olarak geçerli Q# koddur:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

`ourH`Önceki kod parçacığında değişkenin değeri, daha sonra <xref:Microsoft.Quantum.Intrinsic.H> Bu değeri diğer tüm işlemler gibi çağırabilmeniz için işlem olur.
Bu özellik sayesinde, işlemleri girişin bir parçası olarak alan ve daha yüksek sıralı denetim akışı kavramları oluşturan işlemler yazabilirsiniz.
Örneğin, aynı hedef qubit 'e iki kez uygulayarak bir işlemi "kare" olarak düşünün.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>İşlevden işlem döndürme

İşlemler, bir işlem biçiminde bir hisse programın açıklamasını döndüren klasik bir işlev olarak bazı klasik koşullu mantığı ayırabilmeniz için, işlemleri çıktıların bir parçası olarak de döndürebileceğinizi vurgulamanız önemlidir.
Basit bir örnek olarak, iki bitlik bir klasik ileti alan tarafın, bu iletiyi kullanarak doğru bir teleporm durumuna ulaşmasını sağlamak için ileti kullanması gereken teleporsyon örneğini düşünün.
Bunu, bu iki klasik biti alan ve uygun kod çözme işlemini döndüren bir işlev açısından yazabilirsiniz.

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

Bu yeni işlev aslında bir işlevdir, ancak aynı değerleri ve ile çağırırsanız, `hereBit` `thereBit` her zaman aynı işlemi geri alırsınız.
Bu nedenle, kod çözme mantığının farklı işlem özelleştirmelerinin tanımlarına nasıl etkileştiğini fark etmeden güvenli bir şekilde çalışabilir.
Diğer bir deyişle, bir işlev içindeki klasik mantık yalıtılmış ve bu, derleyicinin işlev çağrısının, bir giriş korunduğu sürece Impunity ile yeniden sıralanacağını kabul edilebilir.


## <a name="partial-application"></a>Kısmi uygulama

*Kısmi uygulama* kullanarak işlem döndüren işlevlerle çok daha fazlasını yapabilirsiniz. Bu, bir işleve veya işleme girişin bir veya daha fazla bölümünü gerçekten çağırmadan bir veya daha fazla şekilde sağlarsınız. Önceki örnekte, `ApplyTwice` giriş işleminin hangi qubit 'e uygulanacağını belirtmek istediğinizi belirtmek istemezsiniz:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

Bu durumda, yerel değişken `twiceOp` kısmen uygulanan işlemi tutar; `ApplyTwice(op, _)` burada, `_` girişin henüz belirtilmediği bölümleri gösterir.
`twiceOp`Sonraki satırda çağırdığınızda girişin geri kalan bölümlerinin tümü için kısmen uygulanmış işleme giriş olarak geçiş yapılır.
Bu nedenle, önceki kod parçacığı, doğrudan çağrılmasıyla aynı şekilde, `ApplyTwice(op, target)` Yeni bir yerel değişken sunmuş olduğunuz için kaydedin, böylece girişin bazı parçalarını sağlarken çağrıyı erteleyebilirsiniz.

Kısmen uygulanmış bir işlem, tüm giriş sağlanana kadar gerçekten çağrılmadığı için, işlevleri içinden bile işlemleri güvenle uygulayabilirsiniz.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

Prensibi, içindeki klasik mantık çok `SquareOperation` daha fazla olabilir, ancak derleyicinin işlevler hakkında sunabileceği garantilere göre bir işlemin geri kalanından yalıtılmıştır. Q#Standart kitaplık, klasik denetim akışını, hisse programlarının kullanabileceği bir şekilde ifade etmek için bu yaklaşımı kullanır.


## <a name="recursion"></a>Özyineleme

Q# callables 'in doğrudan veya dolaylı olarak özyinelemeli olmasına izin verilir.
Diğer bir deyişle, bir işlem veya işlev kendisini çağırabilir veya çağrılabilir işlemi doğrudan veya dolaylı olarak çağıran başka bir çağrılabilir çağrısı yapabilir.

Ancak özyineleme kullanımı hakkında iki önemli yorum vardır:

- İşlemlerde özyineleme kullanımı, bazı iyileştirmelere engel olabilir.
  Bu girişim, algoritmanın çalışma süresi üzerinde önemli bir etkiye sahip olabilir.
- Gerçek bir hisse cihazında çalışırken yığın alanı sınırlı olabilir ve bu nedenle derin özyineleme bir çalışma zamanı hatasına neden olabilir.
  Özellikle, Q# derleyici ve çalışma zamanı Kuyruk özyineleme 'yi tanımlamaz ve iyileştirmez.

## <a name="next-steps"></a>Sonraki adımlar

İçindeki [değişkenler](xref:microsoft.quantum.guide.variables) hakkında bilgi edinin Q# .