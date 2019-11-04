---
title: Hartree-Fock teorisi | Microsoft Docs
description: Hartree-Fock teorik belgeleri
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: e73111ae710e11ca6730581b8be711cf32783677
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184109"
---
# <a name="hartreefock-theory"></a>Hartree – Fock teorisi

Hisse kutları benzetiminde en önemli miktar, Hamiltonian matrisin en düşük enerji eigenvector değeri olan zemin durumudur.
Bunun nedeni, yeniden eylem oranları gibi oda sıcaklık miktarlarındaki en fazla motacules 'in, bir yeniden eylem yasındaki adımın başlangıcını ve sonunu betimleyen hisse ve ara sıcaklık durum genellikle taban durumlardır.
Baş durum, genellikle daha fazla bilgi almak için çok zor olsa da (hisse bir bilgisayar ile bile), katlanarak çok sayıda yapılandırma üzerinden bir dağıtım olduğundan.
Zemin eyalet enerji gibi miktarlar öğrenilebilir.
Örneğin, $ \ket{\psı} $ herhangi bir saf hisse durumundaysa, \begin{Equation} E = \bra{\psı} \hat{H} \ket{\psı} \end{Equation}, sistemin o durumda sahip olduğu ortalama enerji sağlar.
Bu durumda, bu değer en küçük değeri veren durumdur. Sonuç olarak, doğru zemin durumu için mümkün olduğunca yakın olan bir durumun seçilmesi, doğrudan enerjiyi tahmin etmek için (değişen bir sanal bölge kapsamında olduğu gibi) ya da aşama tahmini aracılığıyla önemli bir durum seçmektir.

Hartree – Fock teorik, hisse sistemleri için ilk durumu oluşturmak için basit bir yol sağlar. Bir hisse sisteminin zemin durumu için tek bir sdaha daha sonra determinantı verir. Bu uçta, boşluk enerji alanını en aza indiren, Fock-Space içinde bir döndürme bulur. Özellikle, $N $ Elektriklerde bir sistem için yöntem, döndürme \begin{Equation} \prod_{j = 0} ^ {N-1} a ^ \abger_j \tus{0} \mapsto \prod_{j = 0} ^ gerçekleştirir {N-1} e ^ {u} a ^ \abger_j e ^ {-u} \tus{0}\defeq\prod_{j = 0} ^ {N-1} \widetilde{a} ^ \kama ger _j \ket{0}, \end{Equation} bir anti-hermitian (yani $u =-u ^ \linger $) matrisi $u = \sum_{PQ} u_ {PQ} a ^ \linger_p A_Q $. $U $ matrisinin orbilaçlerini ve $ \widetilde{a} ^ \linger_j $ ve $ \widetilde{a}_j $ ' i temsil ettiğinden, elektriksel molesel döndürme-Orbitals için oluşturma ve annimilasyon işleçlerini temsil etmelidir.


$U $ matrisi, daha sonra beklenen enerji $ \bra{0} \prod_{j = 0} ^ {N-1} \widetilde{a}\_j H \prod\_{k = 0} ^ {N-1} \widetilde{a} ^ \dagger_k\ket{0}$ değerini en iyi duruma getirdi. Bu iyileştirme sorunları genel olarak oldukça zor olabilir; böylece, Hartree – Fock algoritması en iyi duruma getirme sorununa hızlı bir şekilde yakınsama eğilimi yaparak, özellikle de eşitlenmiş-Shell molecuları için daha yakın bir çözüm sağlar. Bu durumları `FermionWavefunction` nesnesinin bir örneği olarak belirteceğiz. Örneğin, $a ^ \abger_{1}a ^ \abger_{2}bir ^ \abger_{6}\demet{0}$, aşağıdaki gibi kimya kitaplığında örneği oluşturulur.
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
Ayrıca, `SpinOrbital` dizinlerle dalga işlevlerinin dizinini oluşturup bu dizinleri aşağıdaki gibi tamsayılara dönüştürür.
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

Hartree – Fock teorik özelliği ile ilgili en çarpıcı özellik, Elektriklerde hiçbir entanglement 'e sahip olmayan bir hisse
Bu, genellikle, molesel sistemlerin özelliklerinin uygun bir niteleyici açıklaması sağladığı anlamına gelir. 

Hartree-Fock durumu ayrıca bir `FermionHamiltonian` aşağıdaki şekilde yeniden oluşturulabilir.
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

Bununla birlikte, özellikle de kesin bağıntılı sistemler için doğru sonuçlar elde etmek, Hartatin teorik, çok fazla