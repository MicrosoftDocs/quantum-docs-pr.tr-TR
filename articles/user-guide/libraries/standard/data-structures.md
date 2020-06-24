---
title: 'Q # standart kitaplıklarında veri yapıları'
description: 'Microsoft Q # standart kitaplıklarında veri yapıları, Oracles ve dinamik oluşturucuları hakkında bilgi edinin.'
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 46ac6794d1e21e111aa1d98e11a6f83194f8d54e
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275728"
---
# <a name="data-structures-and-modeling"></a>Veri yapıları ve modelleme #

## <a name="classical-data-structures"></a>Klasik veri yapıları ##

Diğer bir deyişle, örneğin, hisse kavramlarını temsil eden Kullanıcı tanımlı türlerin yanı sıra, Canon 'nin aynı zamanda, hisse sistemleri denetiminde kullanılan klasik verilerle çalışmaya yönelik işlemler, işlevler ve türler de sağlar.
Örneğin, <xref:microsoft.quantum.arrays.reversed> işlev bir diziyi girdi olarak alır ve ters sırada aynı diziyi döndürür.
Bu daha sonra, `Qubit[]` tamsayıların hisse gösterimi arasında dönüştürme yaparken gereksiz $ \operatorname{Swap} $ kapıları uygulamak zorunda kalmamak için türünde bir dizide kullanılabilir.
Benzer şekilde, önceki bölümde form türlerinin `(Int, Int -> T)` rastgele erişim koleksiyonlarını temsil eden yararlı olduğunu gördük. bu nedenle, <xref:microsoft.quantum.arrays.lookupfunction> işlev dizi türlerinden bu tür türleri oluşturmak için kullanışlı bir yol sağlar.

### <a name="pairs"></a>Çiftine ###

Canon, çiftler için işlevsel stil gösterimini destekler, bu, parçalanmaya göre tanımlama gruplarına erişme işlemi tamamlanır:

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a>Diziler ###

Canon, dizileri işlemek için çeşitli işlevler sağlar.
Bu işlevler tür parametreli parametreleridir ve bu nedenle herhangi bir Q # türündeki dizilerle birlikte kullanılabilir.
Örneğin, işlevi, <xref:microsoft.quantum.arrays.reversed> öğeleri girişinden ters sırada olan yeni bir dizi döndürür.
Bu işlem, işlemler çağrılırken bir hisse kayıt 'nın nasıl temsil edileceğini değiştirmek için kullanılabilir:

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

Benzer şekilde, <xref:microsoft.quantum.arrays.subarray> işlevi bir dizinin öğelerinin alt kümelerini düzenlemek veya almak için kullanılabilir:

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

Flow denetimiyle birleştirildiğinde, gibi dizi işleme işlevleri, <xref:microsoft.quantum.arrays.zip> bir hızlı program Express için güçlü bir yol sağlayabilir:

```qsharp
// Applies X₃ Y₁ Z₇ to a register of any size.
ApplyToEach(
    ApplyPauli(_, register),
    Map(
        EmbedPauli(_, _, Length(register)),
        Zip([PauliX, PauliY, PauliZ], [3, 1, 7])
    )
);
```

## <a name="oracles"></a>Oracles ##

[Aşama tahmini](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm) ve [genliği](https://en.wikipedia.org/wiki/Amplitude_amplification) yükseltme belgelerinin bir Oracle kavramı sık görülen bir şekilde görünür.
Burada Oracle terimi, bir qubits kümesi üzerinde davranan ve yanıtı bir aşama olarak döndüren bir kara kutu hisse alt yordamını ifade eder.
Bu alt yordam, genellikle Oracle 'ı kabul eden bir hisse algoritması girişi olarak düşünülebilir, diğer parametrelere ek olarak bir dizi hisse ve bir dizi işlem uygular ve bu hisse için bir çağrı, temel bir geçit gibi bir çağrı sağlar.
Kuşkusuz, büyük algoritmayı gerçekten uygulamak için, Oracle 'ın, temel kapıların somut bir şekilde ayrıştırma sağlanması gerekir, ancak Oracle 'ı çağıran algoritmayı anlamak için bu ayrıştırma gerekmez.
Q # içinde, bu soyutlama, işlemler ilk sınıf değerlerdir ve bu da işlemler, bir siyah kutu halinde hisse algoritmaları uygulamalarına geçirilebilirler.
Ayrıca, Kullanıcı tanımlı türler, farklı Oracle temsillerini tür açısından güvenli bir şekilde etiketlemek için kullanılır. bu sayede, farklı siyah kutu işlemlerini yanlışlıkla daha kolay hale getirmeyi zorlaştırır.

Bu tür Oracles, [Grover 'in arama](https://en.wikipedia.org/wiki/Grover%27s_algorithm) ve hisse simülasyonu algoritmaları gibi çok sayıda örnek de dahil olmak üzere çeşitli bağlamlarda görünür.
Burada yalnızca iki uygulama için gerekli olan Oracles odaklanıyoruz: genliği ve aşama tahmini.
İlk olarak, aşama tahmine geçmeden önce geniz Oracles ' i tartışacağız.

### <a name="amplitude-amplification-oracles"></a>Genliği yükseltme Oracles ###

Genize yükseltme algoritması, durumun bir listesini uygulayarak bir başlangıç durumu ve nihai durum arasında bir döndürme gerçekleştirmeye kadar amaçlar.
Algoritmanın çalışması için, bu durumların her ikisinde de bir belirtime ihtiyacı vardır.
Bu belirtimler iki Oracles tarafından verilir.
Bu Oracles, girdileri iki boşlukla, bir "hedef" alt alanı ve bir "ilk" alt alanı ile kopararak çalışır.
Oracles, bu boşluklara bir $ \pm $1 aşaması uygulayarak Pauli işleçlerinin iki boşluğu nasıl tanımladığından benzer şekilde, bu tür alt boşlukları belirler.
Temel fark, bu boşlukların bu uygulamada yarı boşluk olmaması gerektiğidir.
Ayrıca, bu iki alt boşlukların genellikle birbirini dışlamadığını unutmayın: her iki boşluğun üyesi olan vektörler olacaktır.
Bu doğru değilse, genliği bir etkiye sahip olmaz; bu nedenle, hedef alt alanla sıfır olmayan bir örtüşmeye sahip olması için ilk alt alana ihtiyacımız var.

Aşağıdaki eyleme sahip olacak şekilde, geniz 'nin $P $0 olması için gereken ilk Oracle \_ 'ı göstereceğiz.  "İlk" alt alanındaki tüm durumlar $ \ket{x} $ $P \_ 0 \ket{x} =-\ket{x} $ ve bu alt alanda olmayan tüm durumlar $ \ket{yı} $, $P \_ 0 \ iş {yı} = \ket{yı} $.
$P _1 $ olan hedef alt boşluğu işaretleyen Oracle, tam olarak aynı formu alır.
Hedef alt alanda $ \ket{x} $ tüm durumlar için (örneğin, algoritmanın çıkışını yapmak istediğiniz tüm durumlar için) $P _1 \ ayraç {x} =-\ket{x} $.
Benzer şekilde, hedef alt alanda olmayan tüm durumlar $ \ket{yı} $ $P _1 \ demet {y} = \ket{yı} $.
Bu iki yansıma, daha sonra, genel eksi işaretinin yalnızca denetimli uygulamalarda dikkate alınması açısından önemli olduğu, $Q =-P_0 P_1 $ gibi tek bir genafme adımını sunan bir operatör oluşturacak şekilde birleştirilir.
Genüme daha sonra ilk alt alanda bulunan bir ilk durum olan $ \ket{\psı} $, sonra da $ \ket{\psı} \mapsto Q ^ d \ket{\psı} $ yerine geçer.
Böyle bir yineleme gerçekleştirildiğinde, bir tane, işaretlenen boşluk ile çakışan $ \sin ^ 2 (\teta) $ olan bir başlangıç durumuyla başlıyorsa, bu örtüşme $m $ \sin ^ 2 ([2m + 1] \ teta) $ olur.
Bu nedenle genellikle $ [2m + 1] \teta = \ pi/2 $; gibi ücretsiz bir parametre olmak üzere $m $ öğesini seçmek istiyoruz. Ancak, bu tür rigıd seçimleri, sabit noktalı genlama gibi bazı genlama için önemli değildir.
Bu işlem, işaretleme işlevine quadkıtik sorguları ve tam olarak klasik bir cihazda mümkün olduğunca durum hazırlama işlevini kullanarak işaretli alt alanda bir durum hazırlamanızı sağlar.
Bu nedenle, çok sayıda hisse bilgi işlem uygulaması için önemli bir yapı bloğu budur.

Algoritmanın nasıl kullanılacağını anlamak için, Oracles yapımı veren bir örnek sağlamak yararlı olur.  Bu ayarda, veritabanı aramaları için Grover 'in algoritmasını gerçekleştirmeyi düşünün.
Grover 'in aramasında, amaç $ \ket{+} ^ {\otimes n} = H ^ {\otimes n} \tus$ ' i {0} (potansiyel) çok sayıda işaretlenmiş durumdan birine dönüştürmektir.
Daha fazla basitleşmesi için yalnızca tek işaretli durumun $ \ket $ olduğu duruma göz atalım {0} .
Daha sonra iki Oracles tasarlıyoruz: yalnızca başlangıç durumu $ \ket{+} ^ {\otimes n} $ değerini eksi işareti ile işaretleyen ve işaretli durum $ \ket $ değerini eksi işaretiyle işaretleyen bir tane {0} .
İkinci ağ geçidi, Canon içindeki denetim akışı işlemleri kullanılarak aşağıdaki işlem işlemi kullanılarak uygulanabilir:

```qsharp
operation ReflectAboutAllZeros(register : Qubit[]) : Unit 
is Adj + Ctl {

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);

    // Apply an $n-1$ controlled $Z$-gate to the $n^{\text{th}}$ qubit.
    // This gate will lead to a sign flip if and only if every qubit is
    // $1$, which happens only if each of the qubits were $0$ before step 1.
    Controlled Z(Most(register), Tail(register));

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);
}
```

Bu Oracle daha sonra işlemin özel bir durumdur ve bu da <xref:microsoft.quantum.canon.rall1> , yansıma durumu $ \phi = \pı $ yerine rastgele bir aşamaya göre döndürmeyi sağlar.
Bu durumda, `RAll1` <xref:microsoft.quantum.intrinsic.r1> Prelude işlemine benzerdir. Bu, tek qubit durumu $ \ket $ yerine $ \ket{11\cdots1} $ hakkında daha fazla döner {1} .

İlk alt boşluğu işaretleyen Oracle, benzer şekilde oluşturulabilir.
Sözde kod içinde:

1. Her qubit 'e $H $ Gates uygulayın.
2. Her qubit 'e $X $ Gates uygulayın.
3. ^ {\Text{TH}} $ qubit $n $n-$1 denetimli $Z $-Gate uygulayın.
4. Her qubit 'e $X $ Gates uygulayın.
5. Her qubit 'e $H $ Gates uygulayın.

Bu kez, <xref:microsoft.quantum.canon.applywith> yukarıda açıklanan işlemle birlikte kullanmayı da göstermektedir <xref:microsoft.quantum.canon.rall1> :

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

Daha sonra iki durum arasında bir değer döndürmek için bu iki Oracles birlikte birleştirilebiliyoruz ve $ {0} \sqrt{2 ^ n} ile orantılı olan Hadamard Gates katman sayısını kullanarak $ \ket{+} ^ {\otimes n} $ to $ \tus$ olarak $ (ie $m \propto \sqrt{2 ^ n} $), {0} sonuç $0 $ gözlemlene kadar ilk durum hazırlanarak ve ölçerek $ \ket $ durumunun belirleyici olmayan şekilde hazırlanması için gereken kabaca $2 ^ n $ katman karşılaştırması.

### <a name="phase-estimation-oracles"></a>Aşama tahmini Oracles ###

Aşama tahmini için Oracles biraz daha doğal bir şekilde yapılır.
Aşama tahmini amacı, bir Unitary matrisin eigendeğerlerinden örneklenebilecek bir altyordam tasarlayasağlamaktır.
Bu yöntem, pmistry ve malzemeçlerinde çok sayıda fiziksel sorun olduğundan, bu eigenvalues 'ın, kudüler için malzeme ve reactıon Dynamics 'in aşama diyagramları hakkında değerli bilgiler sunan hisse ve ABD devlet enerjileri için olmazdır.
Her aşama tahmini türü bir giriş Unitary gerektirir.
Bu Unitary, geleneksel iki türden biri tarafından açıklanacaktır.

> [!TIP]
> Aşağıda açıklanan Oracle türlerinin her ikisi de örneklerde ele alınmıştır.
> Sürekli sorgu Oracles hakkında daha fazla bilgi edinmek için lütfen [ **Phasetahmine** örnek](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation)bölümüne bakın.
> Ayrık sorgu Oracles hakkında daha fazla bilgi edinmek için lütfen [ **ısingphasetahmine** örnek](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation)bölümüne bakın.

Oracle 'ın ayrı bir sorgusunu çağırdığımız ve Kullanıcı tanımlı türle temsil ettiğimiz Oracle 'ın ilk türü <xref:microsoft.quantum.oracles.discreteoracle> , yalnızca Unitary matrisini içerir.
$U $, eigenvalues değerlerini tahmin etmek istediğimiz Unitary ise, Oracle for $U $, $U $ uygulayan bir altyordam için yalnızca bir stand olur.
Örneğin, bir tek $U $, genliği tahmin etmek için yukarıda tanımlanan Oracle $Q $ ' ı alabilir.
Bu matrisin eigenvalues değeri, ilk ve hedef durumları arasındaki çakışmayı tahmin etmek için kullanılabilir, ancak daha az sayıda örnek kullanarak $ \sin ^ 2 (\teta) $, aksi halde bir kez daha gerekecektir.
Bu, genal Oracle $Q $ ' i kullanarak, genlik tahmini adı giriş olarak bir aşama tahmini uygulamasını daha fazla edinir.
Hisse Metroloji içinde yaygın olarak kullanılan başka bir ortak uygulama, küçük bir döndürme açısı tahmini içerir.
Diğer bir deyişle, $R _z (\teta) $ biçiminde bilinmeyen bir döndürme kapısı için $ \teta $ değerini tahmin etmek istiyoruz.
Bu gibi durumlarda, ağ geçidi için bu sabit değer olan $ \teta $ değerini öğrenmek için etkileşimde yaptığımız altyordam $ $ \begin{hizalaması} U & = R_z (\teta) \\ \\ & = \begin{bmatrix} e ^ {-i \ teta/2} & 0 \\ \\ 0 & e ^ {ı \ teta/2} \end{bmatrix}.
\end{hizalaması} $ $

Aşama tahmini içinde kullanılan Oracle 'ın ikinci türü, türü tarafından temsil edilen sürekli sorgu Oracle ' dır <xref:microsoft.quantum.oracles.continuousoracle> .
Aşama tahmini için Oracle sürekli sorgusu, $U (t) $, $t $ ' in sınıfda bilinen gerçek bir sayıdır.
$U $ 'in sabit bir Unitary olmasına izin vermemiz halinde sürekli sorgu Oracle, $U (t) = U ^ t $ biçimini alır.
Bu, farklı sorgu modelinde doğrudan uygulanmayan $ \sqrt{U} $ gibi matrisleri sorgulamanızı sağlar.

Bu tür Oracle, belirli bir Unitary 'u araştırmadığınızda, ancak Unitary oluşturucusunun özelliklerini öğrenmek istemeniz halinde değerlidir.
Örneğin, dinamik hisse simülasyonu ' nde amaç, hermitian matris için $U (t) = e ^ {-i H s} $ $H $ ve evlenme süresi $t $.
$U (t) $ öğesinin eigenvalues değeri, $H $ öğesinin eigenvalues ile doğrudan ilgilidir.
Bunu görmek için $H $: $H \ket{E} = E\ket {E} $ ' nin eigenbir vektörünü düşünün; bu durumda $U (t) \ket{E} = e ^ {i\phi} \ demet {E} = e ^ {-iEt} \ket{E} $ olan matris üstel değerinin güç serisi tanımından kolayca görüyoruz.
Bu nedenle $U (t) $ eigenphase tahmini, eigenvector $ \ket{E} $ 'ın aşama tahmin algoritmasına giriş olduğunu varsayarak eigenvalue $E $ değerini verir.
Ancak, bu durumda $t $ değeri yeterince küçük olan $t $ eigenvalue $E $, $E =-\ Phi/t $ aracılığıyla benzersiz bir şekilde ters çevrilenebilir.
Hisse simülasyonu yöntemleri kısmi bir evlenme gerçekleştirme özelliği sunduğundan, bu, özellikle de ayrık sorgu modelinin tamsayı $j $U $ $U ^ j $ biçimindeki yalnızca birimlere izin vermesi durumunda, tek $t yapmanız gereken, bir dizi tahmin algoritmasına Unitary 'ı sorgularken ek bir serbestlik verir
Bu, $E $; hakkında en fazla bilgi sağlayacak olan denemeyi tam olarak seçmemizi sağladığından, son derece tahmin algoritmalarının her birinin en son verimliliğini sıkıştırmanız açısından önemlidir. ayrı sorguları temel alan yöntemler, algoritmadaki sorguların en iyi tamsayı sayısını seçerek ödün vermelidir.

Bunun somut bir örneği olarak, bir ağ geçidinin döndürme açısını değil, bir dönen hisse sisteminin işlem sıklığını tahmin etme sorununu göz önünde bulundurun.
Bu tür hisse dinamikleri tanımlayan Unitary, evlenme süresi $t $ ve bilinmeyen sıklık $ \omega $ için $U (t) = R_z (2 \ Omega t) $ şeklindedir.
Bu bağlamda, tek bir $R _z $ kapısı kullanarak herhangi bir $t $ için $U (t) $ benzetimi yapabiliriz ve bu nedenle kendimize yalnızca Unitary ile ayrı sorgularla sınırlandırması gerekmez.
Benzer bir şekilde, bu tür bir sürekli model, diğer bir deyişle, Logaritmik sorgular kullanan aşama tahmin işlemlerinden, diğer bir deyişle $t $ ' nin yorumsuz değerler üzerinde gerçekleştirilen denemeleri sonuçlarından ortaya çıkacak olan bir özellik elde edebilir.
Bu nedenle, bu sürekli sorgu modelleri gibi sorunlar için Oracle yalnızca uygun değildir ancak ayrık sorgu modeli için de tercih edilir.
Bu nedenle, Q # her iki sorgu formu için işlevlere sahiptir ve bir aşama tahmin algoritmasıyla ilgili olarak gereksinimlerine ve mevcut Oracle türüne göre karar vermek için bunu kullanıcıya bırakır.

## <a name="dynamical-generator-modeling"></a>Dynamical Oluşturucu modelleme ##

Zamanın oluşturanlar, durumların zaman içinde nasıl geliştüini açıklamaktadır. Örneğin, bir hisse adı $ \ket{\psı} $, Schrödinger denklemi $ $ \begin{hizalaması} ı\frac {d \ket{\psı (t)}} {d t} & = H \ket{\psı (t)} öğesine tabidir. \end{hizalaması} $ $ $ $, hermitian matrisi $H $, Hamiltonian olarak bilinen, hareket Oluşturucu olarak bilinir. İlk durum $ \ket{\psı (0)} $ $t = $0, zaman içinde bu denklemin resmi çözümü $t $ olabilir, ilke içinde, matris üstel $U (t) = e ^ {-i H t} $ ' nin Unitary zaman-gelişme işleci olarak bilinmediği $ $ \begin{hizalaması} \ket{\psı (t)} = U (t) \ket{\psı (0)}, \end{hizalaması} $ $ yazılmıştır. Aşağıdaki şekilde bu formun bazı oluşturuculara odaklanıyoruz ancak, kavramı açık hisse sistemleri benzetimi veya daha fazla soyut fark denklemleri gibi daha geniş bir şekilde uygulanacağını vurgularız.

Dinamik simülasyonu 'nin birincil amacı, bir hisse bilgisayarının qubit durumunda kodlanmış bazı hisse alma işlecini uygulamaktır.  Birçok durumda Hamiltonian bazı $d $ daha basit terimlerin toplamına ayrılabilir

$ $ \begin{hizalaması} H & = \sum ^ {d-1} _ {j = 0} H_j, \end{hizalaması} $ $

her dönemin zaman gelişiminde, her dönem için tek bir bilgisayar için kolayca uygulanması kolaydır. Örneğin, $H _j $, qubit yazmacın 1. ve 2. öğelerinde işlem gören bir Pauli $X _1X_2 $ operatöründür `qubits` . Bu, her zaman için, imzası olan işlem çağırarak $t $ uygulanabilir `Exp([PauliX,PauliX], t, qubits[1..2])` `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` . Hamiltonian benzetiminde daha sonra anlatıldığı gibi, bir çözüm daha basit işlemler dizisiyle $H $ ile zaman gelişmede yaklaşık olarak

$ $ \begin{hizalaması} U (t) & = \left (e ^ {-iH \_ 0 t/r} e ^ {-ih \_ 1 t/r} \cnoktalar e ^ {-ih \_ {d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\ | H \_ j \\ | ^ 2 t ^ 2/r), \end{hizalaması} $ $

$r > $0 tamsayısı, yaklaşık hatayı denetler.

Dinamik Oluşturucu modelleme kitaplığı, karmaşık oluşturucuları daha basit bir şekilde kodlamak için bir çerçeve sağlar. Bu tür bir açıklama daha sonra, otomatik olarak ele alınan birçok ayrıntıyı içeren bir simülasyon algoritması için zaman gelişini uygulamak üzere benzetim kitaplığı 'na iletilebilir.

> [!TIP]
> Aşağıda açıklanan dinamik Oluşturucu kitaplığı, örneklerde ele alınmıştır. Şaşırtıcı modele dayalı bir örnek için lütfen [ **ııngators** 'ın örneğine](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/generators)bakın.
> Bir örnek için, [**H2SimulationCmdLine**](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line) ve [**H2SimulationGUI**](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/gui) örneklerine bakın.

### <a name="complete-description-of-a-generator"></a>Oluşturucunun tüm açıklaması ###

En üst düzeyde, bir Hamiltonian 'nin tam bir açıklaması, `EvolutionGenerator` iki bileşeni olan Kullanıcı tanımlı türde bulunur.:

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

`GeneratorSystem`Kullanıcı tanımlı tür, Hamiltonian 'nin klasik bir açıklamasıdır.

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

`Int`Kayıt düzeninin ilk öğesi Hamiltonian içinde $d $ terim sayısını depolar ve ikinci öğe, `(Int -> GeneratorIndex)` $ \{ 0, 1,..., d-1 $ içinde bir tamsayı dizinini, \} `GeneratorIndex` Hamiltonian içindeki her temel terimi benzersiz bir şekilde tanımlayan Kullanıcı tanımlı bir türe eşleyen bir işlevdir. Hamiltonian içindeki terimlerin koleksiyonunu dizi yerine bir işlev olarak ifade ederek `GeneratorIndex[]` , bu, `GeneratorIndex` özellikle de çok sayıda terim içeren Hamiltonians tarif edildiğinde yararlı olan, işlem içi hesaplama için izin verir.

Crucially, tarafından tanımlanan temel terimlerin kolay benzetimini yapma konusunda bir kural sunmamalıdır `GeneratorIndex` . Örnek olarak, temel terimler yukarıda açıklanan Pauli işleçleri olabilir, ancak aynı zamanda hisse maç simülasyonu ve oluşturma işleçlerini yaygın olarak ücretçde olabilecek bir şekilde da kullanabilir. Tek başına,, `GeneratorIndex` işaret ettiği dönem tarafından bir hisse akı devresi olarak uygulanabilir.

Bu, `EvolutionSet` herhangi bir `GeneratorIndex` kurallı kümeden çizilmiş, bir Unitary işlecine, `EvolutionUnitary` bir hisse türü olarak ifade edilen bir Kullanıcı tanımlı tür belirtilerek çözümlenir. , `EvolutionSet` Bir öğesinin nasıl `GeneratorIndex` yapılandırıldığını ve ayrıca mümkün olan bir kümesini tanımlar `GeneratorIndex` .

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a>Pauli Işleç oluşturucuları ###

Somut ve yararlı bir örnek, her biri farklı bir katsayı değeri olan Pauli işleçlerinin toplamı olan Hamiltonians.
$ $ \begin{hizalaması} H & = \sum ^ {d-1} _ {j = 0} a_j H_j, \end{hizalaması} $ $; burada her $ \hat H_j $, Pauli grubundan çizilmiştir. Bu tür sistemler için, `PauliEvolutionSet()` `EvolutionSet` aşağıdaki imzaya sahip bir Pauli Group 'un ve bir katsayı öğesinin bir öğesi tarafından nasıl belirlenebileceği için bir kural tanımlayan türü sağlıyoruz `GeneratorIndex` .

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

Kodlarımızda ilk parametre, `Int[]` $ \Stai\estarrow $0, $ \Hat x\sağtarrow $1, $ \Hat yı\estarrow $2 ve $ \Hat Z\sağtarrow $3 şeklinde bir Pauli String belirtir. İkinci parametre, `Double[]` Hamiltonian Içinde Pauli dizesinin katsayısını depolar. Bu dizinin yalnızca ilk öğesi kullanıldığını unutmayın. Üçüncü parametre, `Int[]` Bu Pauli dizesinin üzerinde hareket eden qubits 'leri dizinleyen ve yinelenen öğe içermemelidir. Bu nedenle, Hamiltonian Term $0,4 \hat X_0 \hat Y_8 \hat I_2 \hat Z_1 $ şöyle gösterilebilir

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

, `PauliEvolutionSet()` `GeneratorIndex` Bu formdan herhangi birini aşağıdaki imzayla bir ile eşleyen bir işlevdir `EvolutionUnitary` .

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

İlk parametre, Unitary evrimi 'nin içindeki katsayı ile çarpılacak bir zaman süresini temsil eder `GeneratorIndex` . İkinci parametre, Unitary 'ın üzerinde davrandığı qubit kayıt ' dir. 

### <a name="time-dependent-generators"></a>Zamana bağımlı oluşturucular ###

Birçok durumda, zamana bağlı oluşturanlar arasında modellemeyi de ilgileniyoruz, Schrödinger denklemi $ $ \begin{hizalaması} ı\frac {d \ket{\psı (t)}} {d t} & = \hat H (t) \ket{\psı (t)}, \end{hizalaması} $ $, Oluşturucu $ \hat H (t) $ ' ın artık zamana bağımlı olduğu gibi olabilir. Bu durum için yukarıdaki zamana bağımsız oluşturuculardan uzantı basittir. `GeneratorSystem`$T $, her zaman Için Hamiltonian 'ın açıklanmasına sahip olmak yerine, Kullanıcı tanımlı türe sahip olmamız gerekir `GeneratorSystemTimeDependent` .

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

İlk parametre, \ [0, 1] $ içindeki bir sürekli zamanlama parametresidir $s ve bu türdeki işlevler bu zamanlama için bir döndürür `GeneratorSystem` . Zamanlama parametresinin, bazı simülasyon $T $, bazı toplam süre için $s = t/T $ gibi fiziksel zaman parametresiyle ilişkili olabileceğini unutmayın. Genellikle, bu durum böyle değildir.

Benzer şekilde, bu oluşturucunun tam bir açıklaması bir gerektirir `EvolutionSet` ve bu nedenle `EvolutionSchedule` Kullanıcı tanımlı bir tür tanımlıyoruz.

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```
