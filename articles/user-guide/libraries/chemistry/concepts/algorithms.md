---
title: Hamiltonian Dynamics benzetimi
description: Hamiltonian benzetimleriyle çalışmak için Trour-Suzuki formüllerini ve qubitişmeyi nasıl kullanacağınızı öğrenin.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
no-loc:
- Q#
- $$v
ms.openlocfilehash: 299eb1484a697ad9d1577aabb44ccb61e908bae3
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834015"
---
# <a name="simulating-hamiltonian-dynamics"></a>Hamiltonian Dynamics benzetimi

Hamiltonian, temel alınan işleçlerin toplamı olarak belirtiledikten sonra, daha sonra iyi bilinen tekniklerin bir konak kullanılarak temel geçit işlemlerine derlenebilir.
Üç verimli yaklaşımlar şunlardır: Suzuki formülleri, birimlere ait doğrusal birleşimler ve qutoleştirme.
Aşağıdaki üç yaklaşımı anladık ve Q# Hamiltonian simülasyon kitaplığını kullanarak bu yöntemlerin nasıl uygulanacağını gösteren somut örneklere sahip ediyoruz.


## <a name="trottersuzuki-formulas"></a>Trour – Suzuki formülleri
Trour – Suzuki formüllerinin arkasındaki fikir basittir: Hamiltonian 'ın, Hamiltonians benzetimi yapma ve sonra toplam evrimini bu daha basit Evolutions bir sıra olarak yaklaşık olarak ifade edin.
Özellikle de $H = \ sum_ {j = 1} ^ m H_j $ Hamiltonian olmalıdır.
Ardından, $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $, bu değer $t \ll $1 olduğunda, bu yaklaşık olarak oluşan hata gözardı edilebilir hale gelir.
$E ^ {-i H t} $ sıradan bir üstel ise, bu her bir hatanın $O (m ^ 2 t ^ 2) $: sıfır olacağını unutmayın.
Bu hata oluşur $e çünkü ^ {-iHt} $, bir işleç üstel ve bunun sonucu olarak, $H _j $ koşullarının çalışmamasından dolayı bu formül kullanılırken bir hata oluştu (*Örneğin*, $H _j H_k H_k, genel olarak).

$T $ büyükse, Trour – Suzuki formülleri, bir kısa saat adımları dizisine ayırarak Dynamics 'in doğru benzetimini yapmak için yine de kullanılabilir.
$R $ ' ın evrimde geçen adım sayısı olmasına izin verin. bu nedenle, her adım $t/r $ için her seferinde çalışır. Daha sonra $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left (\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ right) ^ r + O (m ^ 2 t ^ 2/r), $ $ $r $, $m ^ 2 t ^ 2/\ Epsilon $ olarak ölçeklendirirken, bu hatanın herhangi bir $ \epsilon>$0 için en fazla $ \epsilon $ üzerinden yapılabilir olduğunu gösterir.

Hata koşullarının iptal edildiğini belirten bir işleç üs sırası oluşturarak daha doğru yaklaşık bir daha yakın şekilde oluşturulabilir.
En basit bu formül, ikinci sıra Trour-Suzuki formülü, $ $ U_2 (t) = \left (\ prod_ {j = 1} ^ {m} e ^ {-iH_j t/2R} \ prod_ {j = m} biçimini alır ^ 1 e ^ {-iH_j t/2R} \ right) ^ r = e ^ {-iHt} + O (m ^ 3 t ^ 3/r ^ 2), $ $ $m ^ {3/2} t ^ {3/2}/\sqrt {\ Epsilon} $ olarak ölçeklendirmek için $r $ ' i seçerek herhangi bir $ \epsilon>$0 ' den daha az bir hata olabilir.

Daha yüksek sıralı formüller, özellikle de ($ 2k $) $k>$0 için tek sıra, yinelemeli olarak oluşturulabilir: $ $ U_ {2k} (t) = [U_ {2k-2} (s_k \~ t)] ^ 2 u_ {2k-2} ([1-4s_k] t) [u_ {2k-2} (s_k \~ t)] ^ 2 = e ^ {-iht} + O ((m t) ^ {2k + 1}/r ^ {2k}), $ $ burada $s _K = (4-4 ^ {1/(2k-1)}) ^ {-1} $.

En basit, Suzuki tarafından ilk olarak tanıtılan aşağıdaki dördüncü sıra ($k = $2) formüldür: $ $ U_4 (t) = [U_2 (s_2 \~ t)] ^ 2 U_2 ([1-4s_2] t) [U_2 (s_2 \~ t)] ^ 2 = e ^ {-IHV t} + O (m ^ 5T ^ 5/r ^ 4), $ $ burada $s _2 = (4-4 ^ {1/3}) ^ {-1} $.
Genel olarak, yoğun yüksek sıralı formüller benzer şekilde oluşturulabilir; Bununla birlikte, daha karmaşık tümleştiricileri kullanmanın maliyeti genellikle pek çok pratik sorun için dördüncü sıra avantajlarının dışındadır.

Yukarıdaki stratejilerin çalışmasını sağlamak için, $e ^ {-iH_j t} $ geniş bir sınıfının benzetimini yapmak için bir yönteme ihtiyacımız var.
En basit Hamiltonians ailesi ve en çok faydalı olan, burada kullanabiliriz Pauli işleçleri.
Pauli işleçleri, Clienfford işlemleri (hisse bilgi işlem ortamında standart kapıları) kullanılarak diagonalized olabileceğinden kolayca benzetilir.
Ayrıca, diagonalized olduktan sonra eigenvalues, üzerinde davranabilecekleri qubits 'in eşliği hesaplanırken bulunabilir.

Örneğin, $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $ burada $ $ e ^ {-ı Z \otimes Z t} = \begin{bmatrix} e ^ {-it} & 0 & 0 & 0 \\\
        0 & e ^ {i t} & 0 & 0 \\\
        0 & 0 & e ^ {it} & 0 \\\
        0 & 0 & 0 & e ^ {-it} \end{bmatrix}.
$ $ Burada, $e ^ {-iHt} {00} \tus= e ^ {it} {00} \tus$ ve $e ^ {-iht} {01} \tus= e ^ {-it} {01} \tus$, "$0 $, 1. bit $1 dizesinin eşliği $1 $ iken $0 $,

Pauli işleçleri 'nin üs öğeleri Q# , işlemi kullanarak doğrudan uygulanabilir <xref:microsoft.quantum.intrinsic.exp> :
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

Fermıonic Hamiltonians için, [Ürdün – Wigner ayrıştırma](xref:microsoft.quantum.chemistry.concepts.jordanwigner) , Hamiltonian 'Yi Pauli işleçleri toplamı ile eşleştirir.
Bu, yukarıdaki yaklaşımın Chemistry benzetimi için kolayca uyarlanabilme anlamına gelir.
Aşağıda, "Ürdün-Wigner" içindeki tüm Pauli terimleri üzerinde el ile döngü yerine, aşağıdaki gibi bir simülasyonu nasıl çalıştırdığına ilişkin basit bir örnektir.
Başlangıç noktanızda, sınıfın bir örneği olarak kodda ifade edilen Fermıonic Hamiltonian 'in bir [Ürdün-Wigner kodlaması](xref:microsoft.quantum.chemistry.concepts.jordanwigner) vardır `JordanWignerEncoding` .

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

Simülasyon algoritmaları tarafından tüketilebilir olan Ürdün-Wigner gösteriminin bu biçimi Q# Kullanıcı tanımlı bir türdür `JordanWignerEncodingData` .
İçinde Q# , bu biçim, `TrotterStepOracle` çalışması için gereken diğer parametrelere ek olarak, bir Işleci (Suzuki tümleştirici) kullanarak zaman evrimini yaklaştıran bir operatör döndüren kolay bir işleve geçirilir.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

Bu uygulamada, bu uygulama, [hisse bilgisayarları kullanarak elektronik yapı Hamiltonians simülasyonuna](https://arxiv.org/abs/1001.3855) [ilişkin](https://arxiv.org/abs/1403.1539) bazı iyileştirmeler uygular ve bu, gereken tek qubit döndürme sayısını en aza indirmek ve simülasyon hatalarını azaltmayı sağlar.

## <a name="qubitization"></a>Qubitişleştirme

Qubitişleştirme, hisse ve hisse için hisse
Qubitişleştirme, bir defadan fazla qubits gerektirdiğinden, yöntem, evlenme süresi ve hata toleransı ile en uygun ölçeklendirmeyi kabul eder.
Bu nedenlerden dolayı, genel olarak Hamiltonian Dynamics 'in benzetimini yapmak ve özel olarak elektronik yapı sorununu çözmek için sık kırmızı bir yöntem haline gelmiştir.

Yüksek bir düzeyde, bu, aşağıdaki adımlarla bu işlemleri gerçekleştirir.
İlk olarak, $H = \ sum_j h_j H_j $ Unitary ve hermitian $H _j $ ve $h _j \ge $0.
Bir dizi yansıma gerçekleştirmeyle, qubitişleştirme $ $W = e ^ {\pm i \cos ^ {-1} (H/| h | _1)}, $ $ $ $ $ | h | _1 = \ sum_j | h_j | $ ile eşdeğer bir işleç uygular.
Sonraki adımda, $e ^ {i\pm \ Cos ^ {-1} (E_k/| h | _1)} $, $E _K $ değerinin $H $ ' in eigenvalues değeri ^ {-$e t} $ değerine dönüştürülmesi gerekir.
Bu, [hisse sinyali işleme](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501)dahil olmak üzere çeşitli hisse ve değer dönüştürme yöntemleri kullanılarak elde edilebilir.

Alternatif olarak, yalnızca statik miktarlar isteniyorsa (Hamiltonian 'nin zemin durumu enerjisi gibi), sonucun kosinüsünü alarak sonuçtan zemin durumu enerji tahminini tahmin etmek için doğrudan $W $ ' a kadar [aşama tahmini](xref:microsoft.quantum.libraries.characterization) uygulamayı da yeterli olacaktır.
Bu durum, Spectral dönüştürmesinin, bir hisse değeri dönüştürme yöntemi kullanmak yerine sınıf aracılığıyla gerçekleştirilmesini sağladığından önemlidir.

Daha ayrıntılı bir düzeyde, qubitişleştirme uygulanması Hamiltonian için arabirimler sağlayan iki alt yordam gerektirir.
Trour – Suzuki metotlarından farklı olarak, bu alt yordamlar ücretlendirilir ve uygulamaları, bir mahkeme dayalı simülasyonu için gerekli olacak şekilde, logaritmayı çok daha fazla qubit kullanmayı gerektirmeyecektir.

Karşılık gelen ilk hisse alt yordam $ \operatorname{Select} $ olarak adlandırılır ve her bir $H _j $ ' nin hermitian ve Unitary olarak kabul edildiği \begin{Equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psı}, \end{Equation} olarak kabul edilir.
Bu durum kısıtlayıcı gibi görünse de Pauli işleçlerinin hermitian ve Unitary olduğunu ve bu nedenle hisse kamistry simülasyonu gibi uygulamaların bu çerçeveye doğal olarak düştüğünü hatırlayın.
Büyük olasılıkla tahmin edilecek $ \operatorname{Select} $ işlemi, aslında bir yansıma işlemidir.
Bu, her bir $H _j $ Unitary ve hermitian olduğundan ve dolayısıyla ıdgenvalues $ \pm $1 ' i içerdiğinden, $ \operatorname{Select} ^ 2 \ demet {j} \ket{\psı} = \ket{j} \ket{\psi} $ 'ın bu şekilde görülebilir.

İkinci altyordam $ \operatorname{Prepare} $ olarak adlandırılır.
Select işlemi, her Hamiltonian terimlerinin her biri için tutarlı bir yol sağlarken $H _j $ Prepare alt yordamı $h _j $, \begin{Equation} \operatorname{Prepare}\ket {0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}'e erişmek için bir yöntem sunar.
\end{Equation} ardından, çarpma kontrollü bir aşama kapısı kullanarak $ $ \Lambdad\ket {0} ^ {\otimes n} = \begin{Cases} \- \ket{x} & \Text{If} x = 0 olduğunu görüyoruz \\\
        \ket{x} & \Text{otherwise} \end{Cases}.
$$

$ \Operatorname{Prepare} $ işlemi doğrudan qubitişleştirme içinde kullanılmaz, ancak bunun yerine $ \operatorname{Prepare} $ 'ın $ $ \begin{hizalaması} R &amp; = 1-2 \ operatorname {Prepare} {0} \tus\bra {0} \operatorname{Prepare} ^ {-1} \\ \\ &amp; = \operatorname{Prepare} \lambda \operatorname{Prepare} ^ {-1} oluşturduğunu belirten bir yansıma uygulamak için kullanılır.
\end{hizalaması} $ $

$W $, yürüme işleci, $ \operatorname{Select} $ ve $R $ işlemleri $ $ W = \operatorname{Select} R olarak ifade edilebilir. Bu, "^ {\pm i \cos ^ {-1} (H/| H | _1)} $ $e için eşdeğer bir işleç (bir ıometry 'ye kadar) uygulamak için yeniden görünebilen $ $.

Bu alt yordamlar ' de kolayca ayarlanabilir Q# .
Örnek olarak, $H = X_1 + X_2 + Z_1 Z_2 $ ' nin bulunduğu basit qubit çapraz-şaşırtıcı Hamiltonian 'yi düşünün.
Bu durumda, $ Q# \operatorname{Select} $ işlemini uygulayacak kod tarafından çağrılır <xref:microsoft.quantum.canon.multiplexoperations> , ancak $ \operatorname{Prepare} $ işlemi kullanılarak uygulanabilir <xref:microsoft.quantum.preparation.preparearbitrarystate> .
Hubbard modelinin benzetimini içeren bir örnek, [ Q# örnek](https://github.com/microsoft/Quantum/tree/main/samples/simulation/hubbard)olarak bulunabilir.

Rastgele Kimya sorunları için bu adımları el ile belirtmek çok çaba gerektirir, bu da Kimya kitaplığı kullanmaktan kaçınılmaz.
Yukarıdaki Trour – Suzuki simülasyon algoritmasına benzer şekilde,, `JordanWignerEncodingData` `QubitizationOracle` çalışması için gereken diğer parametrelere ek olarak, yürüme işlecini döndüren kolaylık işlevine geçirilir.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

Daha da önemlisi, uygulama <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> Pauli dizelerinin doğrusal bir birleşimi olarak belirtilen rastgele Hamiltonians için geçerlidir.
Kimya benzetimleri için en iyi duruma getirilmiş bir sürüm kullanılarak çağrılır <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle> .
Bu sürüm, [Doğrusal t karmaşıklığıyla, elektronik Spectra 'in, doğrusal bir şekilde kodlama](https://arxiv.org/abs/1805.03662)bölümünde ele alınan teknikleri kullanarak T geçitleri sayısını en iyi duruma getirdi.
