---
title: 'İşlemler ve işlevler-Q # teknikleri | Microsoft Docs'
description: 'İşlemler ve işlevler-Q # teknikleri'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 1fca20bb44cc42008f7d25d2fc71a39b962525c2
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820785"
---
# <a name="q-operations-and-functions"></a>S # Işlem ve Işlevleri

S # programları, bir veya daha fazla *işlemden* oluşur. Bu işlem, bir veya daha fazla işlem ve klasik verilerde değişikliklere izin veren bir veya daha fazla *işlev* olabilir. İşlemlere karşılık işlevler, tamamen klasik davranışı betimleyen ve klasik çıkış değerlerini hesaplama konusunda herhangi bir etkiye sahip olmayan işlevler için kullanılır.

Q # içinde tanımlanan her işlem, dil tarafından tanımlanan yerleşik iç işlemler de dahil olmak üzere herhangi bir sayıda işlemi çağırabilir. Bu iç işlemlerin tanımlandığı belirli yol, hedef makineye bağlıdır. Derlendiğinde, her işlem hedef makinelere sağlanlenebilecek bir .NET sınıf türü olarak temsil edilir.

## <a name="defining-new-operations"></a>Yeni Işlemleri tanımlama

Yukarıda açıklandığı gibi, Q # dilinde yazılmış bir hisse programının en temel yapı taşı, klasik .NET uygulamalarından çağrılabilen bir *işlemdir*. Örneğin, simülatör veya Q # içindeki diğer işlemler tarafından çağrılabilir.
Her işlem bir girdi alır, bir çıktı üretir ve bir veya daha fazla işlem uzmanlığını için uygulamayı belirtir.
Örneğin, aşağıdaki işlem yalnızca bir varsayılan gövde özelleştirmesi tanımlar ve giriş olarak tek bir qubit alır, ardından bu girişte yerleşik `X` işlemini çağırır:

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

Anahtar sözcüğü `operation` işlem tanımını başlatır ve ardından adı gelir; Burada `BitFlip`.
Sonra, girişin türü, yeni işlemdeki girişe başvurmak için bir ad `target` birlikte `Qubit`olarak tanımlanır.
Benzer şekilde, `Unit` işlemin çıktısının boş olduğunu tanımlar.
Bu, ve diğer zorunlu dillerde `void` C# benzer ve içindeki F# `unit` ve diğer işlevsel dillerde eşdeğerdir.

> [!NOTE]
> Bu konuda daha ayrıntılı bilgiler bulabilirsiniz, ancak her Q # işlemi tam olarak bir giriş alır ve tam olarak bir çıktı döndürür.
> Birden çok giriş ve çıkış daha sonra birden çok değeri tek bir değerde toplamak için *Tanımlama grupları*kullanılarak temsil edilir.
> Bu durumda, Q # ' ın bir "demet oluşturma" dili olduğunu varsayalım.
> Bu kavramı izleyerek, `()` `Unit`tür olan "boş" kayıt düzeni olarak okunmalıdır.

Yeni işlem içinde, yalnızca varsayılan gövde özelleştirmesi uygulamasının açıkça belirtilmesi gerekiyorsa, uygulama doğrudan bildirim içinde belirtilebilir. Ayrıca, örneğin, bir veya daha fazla `functor` işlemi için aşağıda ayrıntılı gibi uygulamaları tanımlamak mümkündür. Yukarıdaki örnekte, tek bildiri yerleşik Q # işlemini <xref:microsoft.quantum.intrinsic.x>çağırmadır.

İşlemler ayrıca `Unit`daha ilginç türler döndürebilir.
Örneğin, <xref:microsoft.quantum.intrinsic.m> işlemi, ölçüm gerçekleştirmemiş olduğunu temsil eden `Result`türünde bir çıktı döndürür. Bir işlemden çıkışı başka bir işleme geçirebiliriz ya da yeni bir değişken tanımlamak için `let` anahtar sözcüğüyle kullanabilirsiniz.
<!-- Link to UID for superdense conceptual and example documentation. -->
Bu, yoğun kodlama gibi düşük bir düzeyde hisse uygun olan klasik hesaplamayı temsil etmenizi sağlar:

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a>Funörler, adjoint ve kontrollü
Bir işlem Unitary dönüştürmesi uygularsa, *adjointed* veya *denetimli*olduğunda işlemin nasıl davrandığını tanımlamak mümkündür. Bir işlemin adeksiz özelleştirmesi, geriye doğru çalıştırıldığında bir işlemin nasıl davrandığının, denetimli bir özelleşmenin, bir hisse kayıt durumuna göre uygulanması durumunda işlemin nasıl davrandığının belirtir.
Bu uzmanlıklar, işlem imzasının bir parçası olarak bildirilebilecek: aşağıdaki örnekte `is Adj + Ctl`. Bu tür örtülü olarak tanımlanmış her özelleştirme için karşılık gelen uygulama derleyici tarafından oluşturulur. 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> Q # ' daki birçok işlem Unitary kapılarını temsil eder.
> $U $, bir işlem `U`temsil eden Unitary kapısıdır `Adjoint U`, "^ \dağılım $ $U Unitary geçidini temsil eder.

Uygulamanın derleyici tarafından üretilebileceği durumda, açıkça belirtilebilir. Bu tür açık özelleşmeler, uygun bir oluşturma yönergesinin veya Kullanıcı tanımlı bir uygulamadan oluşabilir. Örneğin, yukarıdaki `PrepareEntangledPair` kod, açık özelleştirme bildirimlerini içeren aşağıdaki koda eşdeğerdir: 

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
Yukarıdaki örnekte, `adjoint invert;`, adjoint özelleşmesinin gövde uygulamasını tersine getirerek oluşturulacağını ve `controlled adjoint invert;` denetlenen majoint özelleşmesinin, denetlenen özelleşmenin belirtilen uygulamasını tersine ayırarak oluşturulacağını belirtir.

Daha [yüksek sıralı Denetim akışında](xref:microsoft.quantum.concepts.control-flow)buna daha fazla örnek görüyoruz.

Bir işlemin özelleşmesi çağırmak için `Adjoint` veya `Controlled` anahtar sözcüklerini kullanın.
Örneğin, yukarıdaki üst bilgi kodlama örneği, entangled durumunun bir qubit çiftiyle geri dönüştürülmesi için `PrepareEntangledPair` adjoint kullanılarak daha fazla sıkı yazılabilir:

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

Funlar ile kullanım için işlemleri tasarlarken göz önünde bulundurmanız gereken bazı önemli sınırlamalar vardır.
Aynı etkiyi elde etmek için bu tür bir işlemde deyimleri yeniden sıralamak belirsiz olduğundan, başka bir işlemin çıkış değerini kullanan bir işlem için en kritik öneme sahip olan uzmanlık, derleyici tarafından otomatik olarak üretilemez.


## <a name="defining-new-functions"></a>Yeni Işlevleri tanımlama

Q #, bir çıkış değeri hesaplamasının ötesinde etkileri olmasına izin verilmediği için işlemlerden farklı olan *işlevleri*tanımlamaya de olanak tanır.
Özellikle, işlevler işlemleri çağıramaz, qubits üzerinde işlem, örnek rastgele sayılar veya başka türlü giriş değerinin ötesinde bir işleve bağımlı duruma bağlıdır.
Sonuç olarak, Q # işlevleri *saf*olduğundan, her zaman aynı giriş değerlerini aynı çıkış değerleriyle eşleştirirler.
Bu, Q # derleyicisinin, işlem uzmanlıklarını oluştururken işlevleri nasıl ve ne zaman çağırdığını güvenle yeniden sıralamak için izin verir.

Bir işlev tanımlamak, bir işlev için hiçbir adjoint veya denetimli uzmanlık tanımlanmamasının dışında, bir işlemi tanımlamaya benzer şekilde çalışır.
Örneğin:

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
Bunu yapmak mümkün olduğunda, işlemler içinden daha kolay bir şekilde kullanılabilmesi için klasik mantığı işlemler yerine işlevler bakımından yazmak yararlıdır.
Örneğin, bir işlem olarak `Square` yazdık, derleyici aynı girişe çağrı yapan aynı çıktıyı tutarlı bir şekilde ürettireceğiz.

İşlevler ve işlemler arasındaki farkın altını bir şekilde çözmek için, bir Q # işlemi içinden rastgele bir sayı örnekleme sorununu ele alalım:

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

`U` her çağrıldığında, `target`farklı bir eyleme sahip olur.
Derleyici, `U`için `adjoint auto` bir özelleştirme bildirimi eklediğimiz takdirde, `U(target); Adjoint U(target);` kimlik (yani, No-Op) olarak hareket eder.
Bu, [vektörlerin ve matrislerde](xref:microsoft.quantum.concepts.vectors)gördüğdiğimiz adjoint 'in tanımını ihlal ediyor. bu şekilde, işlemi çağırdığımız bir işlemde bir adjoint özelleşmesinin otomatik olarak oluşturmaya izin veren <xref:microsoft.quantum.math.randomreal>, derleyici tarafından verilen garantileri bozuyor; <xref:microsoft.quantum.math.randomreal>, hiçbir adjoint veya kontrollü sürüm bulunmayan bir işlemdir.

Öte yandan, `Square` gibi işlev çağrılarına izin vermek, derleyicinin çıktının kararlı kalmasını sağlamak için yalnızca `Square` girişi korumasının gerektiği konusunda emin olabilir.
Bu nedenle, işlevlerde mümkün olduğunca klasik mantığı yalıtmak, diğer işlevlerde ve işlemlerde bu mantığı yeniden kullanmayı kolaylaştırır.

## <a name="control-flow"></a>Denetim Akışı

Bir işlem veya işlev içinde her bir ifade, en sık kullanılan zorunlu klasik dillere benzer şekilde sırayla yürütülür.
Bu denetim akışı, ancak üç farklı şekilde değiştirilebilir:

- `if` deyimleri
- `for` döngüleri
- `repeat`-`until` döngüleri

[Başarılı olana kadar yineleme (ru)](xref:microsoft.quantum.techniques.qubits#measurements) devrelerine kadar, son tartışmayı erteliyoruz.
Ancak `if` ve `for` denetim akışı yapıları, klasik programlama dillerinin çoğu için tanıdık bir anlata devam ediyor.
Özellikle, bir `if` deyimi bir koşul alabilir, bir veya daha fazla `elif` deyimi gelebilir ve bir `else`ile bitemez:

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

Benzer şekilde, `for` döngüleri bir dizi tamsayı veya bir dizinin öğeleri üzerinde yinelemeyi gösterir:

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

Önemlisi, `for` döngüleri ve `if` deyimleri, özelleştirilmiş oluşturmaları otomatik olarak oluşturulan işlemlerde bile kullanılabilir. Bu durumda `for` döngüsünün adeki yönü tersine çevirir ve her yinelemenin adeklerini alır.
Bu, "ayakkabılar-ve-SOCKS" ilkesini izler: Socks ' yi almayı geri almak istiyorsanız, ve ardından
Bu işlem, siz de daha az bir işlem yapmaya çalışır.

## <a name="operations-and-functions-as-first-class-values"></a>Ilk sınıf değerleri olarak işlemler ve Işlevler

İşlemler yerine işlevleri kullanarak denetim akışı ve klasik mantık hakkında önemli bir tekniktir, bu işlemler ve Q # içindeki işlevler *birinci sınıf*olur.
Diğer bir deyişle, her bir değer kendi sağ tarafındaki dilde değerlerdir.
Örneğin, daha az dolaylı bir değer varsa, aşağıdakiler mükemmel bir Q # kodudur:

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

Yukarıdaki kod parçacığında `ourH` değişkenin değeri, işlem <xref:microsoft.quantum.intrinsic.h>ve bu değeri diğer tüm işlemler gibi çağırabiliriz.
Bu, daha yüksek sıralı denetim akışı kavramlarını oluşturan, işlemleri girişin bir parçası olarak alan işlemleri yazmamızı sağlar.
Örneğin, aynı hedef qubit 'e iki kez uygulanarak bir işlemi "kare" olarak ele geçirebilir.

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

Bu örnekte, tür `(Qubit => Unit)` görüntülenen `=>` ok, giriş `op` alanının, türü `Qubit` giriş olarak alan ve çıktısı olarak boş bir tanımlama grubu üreten bir işlem olduğunu gösterir.
Ayrıca, bu işlem türünün özelliklerini belirttik ve bu, hangi funın desteklendiği hakkındaki bilgileri içerir.
`(Qubit => Unit)` bir işlem `Adjoint` veya `Controlled` functor desteklemiyor. Bu tür bir işlemin, örneğin `Adjoint` functor desteğine sahip olduğunu belirtmek istiyoruz, bunu adjointable olarak bildirmemiz gerekir. Bu, türü `is Adj` ek açıklama kullanılarak yapılır. Benzer şekilde, `(Qubit => Unit is Ctl)` bu tür bir işlemin `Controlled` functor 'ı desteklediğini gösterir. Bu konuda [Q # ' daki türler (XREF: Microsoft. hisse. Language. Type-model) daha genel olarak tartışıyoruz.

Şimdilik, işlem biçiminde bir hisse programının açıklamasını döndüren klasik bir işlev olarak bazı klasik koşullu mantığı ayırabilmemiz gibi, işlemleri çıkışların bir parçası olarak de döndürebiliriz.
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

Bu yeni işlev, `hereBit` ve `thereBit`aynı değerlerle çağırırsanız, her zaman aynı işlemi geri alacak.
Bu nedenle, kod çözme mantığının farklı işlem özelleştirmelerinin tanımlarıyla nasıl etkileşime gireceğini öğrenmek zorunda kalmadan güvenli şekilde işlemler içinde çalıştırılabilir.
Diğer bir deyişle, bir işlev içinde klasik mantığı yalıtdık ve bu, bir derleyicinin işlev çağrısının Impunity ile yeniden düzenlenmesine ve girişin korunduğu sürece bir şekilde yeniden sıralanacağını kabul ettik.

Ayrıca, [işlemler ve işlev türlerini](#operations-and-functions-as-first-class-values)tartıştığımız zaman daha ayrıntılı olarak göreceğiniz için işlevleri birinci sınıf değerler olarak kabul eteceğiz.

## <a name="partially-applying-operations-and-functions"></a>Işlemler ve Işlevler kısmen uygulanıyor

*Kısmi uygulama*kullanarak işlem döndüren işlevlerle çok daha fazlasını yapabiliriz, burada, girişin bir veya daha fazla bölümünü bir işleve veya işleme bir veya daha fazla şekilde aramadan sağlayabiliriz. Örneğin, yukarıdaki `ApplyTwice` örneğini geri çektireceğiz, giriş işleminin hangi qubit 'e uygulanacağını, doğru bir şekilde belirtmek istediğimiz belirtebiliriz:

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

Bu durumda `twiceOp` yerel değişkeni, henüz belirtilmemiş olan girişlerin `_`tarafından belirtildiği, kısmen uygulanan işlem `ApplyTwice(op, _)`barındırır.
Aslında bir sonraki satırda `twiceOp` çağırdığımızda, girişin geri kalan bölümlerinin tümü için kısmen uygulanmış işleme giriş olarak geçeceğiz.
Bu nedenle, yukarıdaki kod parçacığı, `ApplyTwice(op, target)` doğrudan çağrılmasıyla daha da benzer bir şekilde, girişin bazı parçalarını sağlarken çağrıyı gecikmemizi sağlayan yeni bir yerel değişken sunuyoruz.

Kısmen uygulanmış bir işlem, tüm giriş sağlanana kadar gerçekten çağrılmadığı için, işlevleri içinden bile işlemleri güvenle uygulayabilirsiniz.

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

Prensibi, `SquareOperation` içindeki klasik mantık çok daha fazla olabilir, ancak derleyicinin işlevleri hakkında sunabileceği garantilere göre, hala işlemin geri kalanından yalıtılmıştır.
Bu yaklaşım, klasik denetim akışını hisse uygun şekilde kullanılmak üzere bir şekilde ifade etmek için Q # standart kitaplığı genelinde kullanılacaktır.
