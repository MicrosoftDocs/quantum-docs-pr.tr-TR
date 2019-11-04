---
title: Hamiltonian Dynamics benzetimi | Microsoft Docs
description: Hamiltonian Dynamics kavramsal docs benzetimi yapma
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 905b03478d453e475fc1e49ea5f88dd0cd2704bc
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184075"
---
# <a name="simulating-hamiltonian-dynamics"></a>Hamiltonian Dynamics benzetimi

Hamiltonian, temel alınan işleçlerin toplamı olarak belirtiledikten sonra, daha sonra iyi bilinen tekniklerin bir konak kullanılarak temel geçit işlemlerine derlenebilir.
Üç verimli yaklaşımlar şunlardır: Suzuki formülleri, birimlere ait doğrusal birleşimler ve qutoleştirme.
Aşağıdaki üç yaklaşımı anladık ve Hamiltonian simülasyon kitaplığını kullanarak bu yöntemlerin nasıl uygulanacağını gösteren somut Q # örnekleri verilmiştir.


## <a name="trottersuzuki-formulas"></a>Trour – Suzuki formülleri
Trour – Suzuki formüllerinin arkasındaki fikir basittir: Hamiltonian 'ın, Hamiltonians benzetimi yapma ve sonra toplam evrimini bu daha basit Evolutions bir sıra olarak yaklaşık olarak ifade edin.
Özellikle de $H = \sum_{j = 1} ^ m H_j $ 'ın Hamiltonian olmasına izin verin.
Ardından, $ $ e ^ {-i\sum_ {j = 1} ^ m H_j t} = \prod_{j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $, bu değer $t \ll $1 olduğunda, bu değer altındaki hatanın yok edilebilir olduğunu varsayalım
$E ^ {-i H t} $ sıradan bir üstel ise, bu her bir hatanın $O (m ^ 2 t ^ 2) $: sıfır olacağını unutmayın.
Bu hata oluşur $e çünkü ^ {-iht} $ bir işleç üstel ve bunun sonucu olarak, $H _j $ koşullarının ulaşım (*örn.* $H _j H_k \ne H_k H_j $ genel) olması nedeniyle bu formül kullanılırken bir hata oluştu.

$T $ büyükse, Trour – Suzuki formülleri, bir kısa saat adımları dizisine ayırarak Dynamics 'in doğru benzetimini yapmak için yine de kullanılabilir.
$R $ ' ın evrimde geçen adım sayısı olmasına izin verin.
Daha sonra $ $ e ^ {-i\sum_ {j = 1} ^ m H_j t} = \left (\prod_{j = 1} ^ m e ^ {-iH_j t/r} \ right) ^ r + O (m ^ 2 t ^ 2/r) $ $ $r $, $m ^ 2 t ^ 2/\ Epsilon $ olarak ölçeklendirirken, hatanın herhangi bir $ \epsilon için en fazla $ \epsilon $ üzerinde yapılabilir olması anlamına gelir > 0 $.

Hata koşullarının iptal edildiğini belirten bir işleç üs sırası oluşturarak daha doğru yaklaşık bir daha yakın şekilde oluşturulabilir.
Bu tür bir en basit formül, simetrik araba formülü veya Yabang bölme, $ $ U_1 (t) = \prod_{j = 1} ^ m e ^ {-iH_j t/2} \ Prod_ {j = m} ^ 1 e ^ biçimini alır {-iH_j t} = e ^ {-iHt} + O (m ^ 3 t ^ 3), $ $ herhangi bir $ için $ \epsilon $ değerinden daha az hale getirilebilir \epsilon > 0 $ $ ' i seçerek $m ^ {3/2} t ^ {3/2}/\sqrt {\ Epsilon} $ olarak ölçeklendirmek için r $.

Hatta daha yüksek sıralı bir sorun, $U _1 $ ' ye göre oluşturulabilir.
En basit, aşağıdaki dördüncü düzen formülüdür. ilk olarak Suzuki tarafından tanıtılan: $ $ U_2 (t) = U_1 ^ 2 (s_1t) U_1 ([1-4s_1] t) U_1 ^ 2 (s_1 t) = e ^ {-iHt} + O (m ^ 5T ^ 5), $ $ burada $s _1 = (4-4 ^ {1/3}) ^{-1}$.
Genel olarak, yoğun yüksek sıralı formüller benzer şekilde oluşturulabilir; Bununla birlikte, daha karmaşık tümleştiricileri kullanmanın maliyeti genellikle pek çok pratik sorun için dördüncü sıra avantajlarının dışındadır.

Yukarıdaki stratejilerin çalışmasını sağlamak için, $e ^ {-iH_j t} $ geniş bir sınıfının benzetimini yapmak için bir yönteme ihtiyacımız var.
En basit Hamiltonians ailesi ve en çok faydalı olan, burada kullanabiliriz Pauli işleçleri.
Pauli işleçleri, Clienfford işlemleri (hisse bilgi işlem ortamında standart kapıları) kullanılarak diagonalized olabileceğinden kolayca benzetilir.
Ayrıca, diagonalized olduktan sonra eigenvalues, üzerinde davranabilecekleri qubits 'in eşliği hesaplanırken bulunabilir.

Örneğin, $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $ burada $ $ e ^ {-ı Z \otimes Z t} = \begin{bmatrix} e ^ {-it} & 0 & 0 & 0 \\\
        0 & e ^ {i t} & 0 & 0 \\\
        0 & 0 & e ^ {it} & 0 \\\
        0 & 0 & 0 & e ^ {-it} \end{bmatrix}.
$ $ Burada, $e ^ {-iHt} \demet{00} = e ^ {it} \tus{00}$ ve $e ^ {-iHt} \tus{01} = e ^ {-it} \tus{01}$, bu da doğrudan $0 $ ' in eşlik eden $, $0 $, bit dizesinin eşlik düzeyi $1 $1 $ olduğunda,

Pauli işleçlerinin üsleri, <xref:microsoft.quantum.primitive.exp> işlemi kullanılarak doğrudan Q # içinde uygulanabilir:
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies e^{- i X \otimes X t} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

Fermıonic Hamiltonians için, [Ürdün – Wigner ayrıştırma](xref:microsoft.quantum.chemistry.concepts.jordanwigner) , Hamiltonian 'Yi Pauli işleçleri toplamı ile eşleştirir.
Bu, yukarıdaki yaklaşımın Chemistry benzetimi için kolayca uyarlanabilme anlamına gelir.
Aşağıda, Ürdün-Wigner temsilindeki tüm Pauli terimleri üzerinde el ile döngü yapmak yerine, aşağıdaki gibi bir simülasyonu nasıl yürütüp bakacağından basit bir örnektir.
Başlangıç noktanızda, `JordanWignerEncoding` sınıfının bir örneği olarak kodda ifade edilen Fermıonic Hamiltonian 'nin bir [Ürdün-Wigner kodlaması](xref:microsoft.quantum.chemistry.concepts.jordanwigner) vardır.

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

Bu, Q # benzetim algoritmaları tarafından tüketilebilir olan Ürdün-Wigner reprsentation biçimi Kullanıcı tanımlı `JordanWignerEncodingData`türüdür.
Q # içinde, bu biçim, yürütülmesi için gereken diğer parametrelere ek olarak, bir işleci (Suzuki tümleştirici) kullanarak zaman elde eden bir operatör döndüren bir kullanışlı işleve geçirilir `TrotterStepOracle`.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

Bu uygulamada, bu uygulama, [hisse bilgisayarları kullanarak elektronik yapı Hamiltonians simülasyonu](https://arxiv.org/abs/1001.3855) konusunda ele alınan bazı iyileştirmeler uygular ve [hisse](https://arxiv.org/abs/1403.1539) tek qubit döndürmeler gerekli, ayrıca simülasyon hatalarını azaltır.

## <a name="qubitization"></a>Qubitişleştirme

Qubitişleştirme, hisse ve hisse için hisse
Qubitişleştirme, bir defadan fazla qubits gerektirdiğinden, yöntem, evlenme süresi ve hata toleransı ile en uygun ölçeklendirmeyi kabul eder.
Bu nedenlerden dolayı, genel olarak Hamiltonian Dynamics 'in benzetimini yapmak ve özel olarak elektronik yapı sorununu çözmek için sık kırmızı bir yöntem haline gelmiştir.

Yüksek bir düzeyde, bu, aşağıdaki adımlarla bu işlemleri gerçekleştirir.
İlk olarak, Unitary ve hermitian $H _j $ ve $h _j \ ge $0 için $H = \sum_j h_j H_j $ ' ye izin verin.
Bir dizi yansıma gerçekleştirmeyle, qubitişleştirme $ $W = e ^ {\pm i \cos ^{-1}(H/| h | _1)}, $ $ $ $ $ | h | _1 = \sum_j | h_j | $ ile eşdeğer bir işleç uygular.
Sonraki adım, $e ^ {i\pm \cos ^{-1}(E_k/| h | _1)} $ konumundaki yürüme işlecinin ıdgenvalues değerlerini dönüştürmeyi içerir; burada $E _K $, $H $ ' in eigenvalues of ^ {-iE_k t} $ $e.
Bu, [hisse sinyali işleme](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501)dahil olmak üzere çeşitli hisse ve değer dönüştürme yöntemleri kullanılarak elde edilebilir.

Alternatif olarak, yalnızca statik miktarlar isteniyorsa (Hamiltonian 'nin zemin durumu enerjisi gibi), sonucun kosinüsünü alarak sonuçtan zemin durumu enerji tahminini tahmin etmek için doğrudan $W $ ' a kadar [aşama tahmini](xref:microsoft.quantum.libraries.characterization) uygulamayı da yeterli olacaktır.
Bu durum, Spectral dönüştürmesinin, bir hisse değeri dönüştürme yöntemi kullanmak yerine sınıf aracılığıyla gerçekleştirilmesini sağladığından önemlidir.

Daha ayrıntılı bir düzeyde, qubitişleştirme uygulanması Hamiltonian için arabirimler sağlayan iki alt yordam gerektirir.
Trour – Suzuki metotlarından farklı olarak, bu alt yordamlar ücretlendirilir ve uygulamaları, bir mahkeme dayalı simülasyonu için gerekli olacak şekilde, logaritmayı çok daha fazla qubit kullanmayı gerektirmeyecektir.

Karşılık gelen ilk hisse alt yordam $ \operatorname{Select} $ olarak adlandırılır ve her bir $H _j $ 'nin olduğu varsayılır. Bu, her bir _j $ 'ın olduğu varsayılabileceği \begin{Equation} \operatorname{Select} \ket{j} \ket{\psı} = \ket{j} H_j \ket{\psı}, \end{Equation}. ve Unitary.
Bu durum kısıtlayıcı gibi görünse de Pauli işleçlerinin hermitian ve Unitary olduğunu ve bu nedenle hisse kamistry simülasyonu gibi uygulamaların bu çerçeveye doğal olarak düştüğünü hatırlayın.
Büyük olasılıkla tahmin edilecek $ \operatorname{Select} $ işlemi, aslında bir yansıma işlemidir.
Bu, her bir $H _j $ Unitary ve hermitian olduğundan ve dolayısıyla ıdgenvalues $ \pm $1 ' i içerdiğinden, $ \operatorname{Select} ^ 2 \ demet {j} \ket{\psı} = \ket{j} \ket{\psi} $ tarafından görülebilir.

İkinci altyordam $ \operatorname{Prepare} $ olarak adlandırılır.
Select işlemi, her Hamiltonian terimlerinin her biri için tutarlı bir yol sağlarken $H _j $ Prepare alt yordamı, $h _j $, \begin{Equation} \operatorname{Prepare}\ket{0} = \sum_j \ sqrt{\frac{h_j}} öğesine erişmek için bir yöntem sağlar | h | _1}} \ket{j}.
\end{Equation} sonra, çarpma kontrollü bir aşama kapısı kullanarak $ $ \Lambdad\ket{0}^ {\otimes n} = \begin{Cases} \-\ket{x} & \Text{If} x = 0 \\\
        \ket{x} & \Text{otherwise} \end{Cases}.
$$

$ \Operatorname{Prepare} $ işlemi doğrudan qubitişleştirme içinde kullanılmaz, ancak bunun yerine $ \operatorname{Prepare} $ 'ın $ $ \begin{hizalaması} R &amp; = 1-2 \ operatorname {Prepare} \tus{0}\bra @no_ oluşturduğu durum hakkında bir yansıma uygulamak için kullanılır. _t_2_ \operatorname{Prepare} ^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^{-1}.
\end{hizalaması} $ $

$W $, yürüme işleci, $ \operatorname{Select} $ ve $R $ işlemleri $ $ W = \operatorname{Select} R olarak ifade edilebilir. Bu, "^ {\pm i \cos ^{-1}(H/| H | _1)} $ $e için eşdeğer bir işleç (bir ıometry 'ye kadar) uygulamak için yeniden görülebilir.

Bu alt yordamlar, Q # ' da kolayca ayarlanabilir.
Örnek olarak, $H = X_1 + X_2 + Z_1 Z_2 $ olan basit qubit çapraz-şaşırtıcı Hamiltonian 'yi düşünün.
Bu durumda, $ \operatorname{Select} $ işlemini uygulayacak olan Q # kodu <xref:microsoft.quantum.canon.multiplexoperations>tarafından çağrılır, ancak $ \operatorname{Prepare} $ işlemi <xref:microsoft.quantum.preparation.preparearbitrarystate>kullanılarak uygulanabilir.
Hubbard modelinin benzetimini yapmayı içeren bir örnek, bir [Q # örneği](https://github.com/Microsoft/Quantum/tree/master/Samples/src/HubbardSimulation)olarak bulunabilir.

Rastgele Kimya sorunları için bu adımları el ile belirtmek çok çaba gerektirir, bu da Kimya kitaplığı kullanmaktan kaçınılmaz.
Yukarıdaki Trour – Suzuki simülasyon algoritmasına benzer şekilde, `JordanWignerEncodingData`, yürütülmesi için gereken diğer parametrelere ek olarak, yürüme işlecini döndüren `QubitizationOracle` kolaylık işlevine geçirilir.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
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
Kimya benzetimleri için en iyi duruma getirilmiş bir sürüm <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>kullanılarak çağrılır.
Bu sürüm, [Doğrusal t karmaşıklığıyla, elektronik Spectra 'in, doğrusal bir şekilde kodlama](https://arxiv.org/abs/1805.03662)bölümünde ele alınan teknikleri kullanarak T geçitleri sayısını en iyi duruma getirdi.
