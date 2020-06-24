---
title: Hartree-Fock teorisi
description: Hisse sistemleri için ilk durumu oluşturmanın basit bir yolu olan Hartree – Fock teorisi hakkında bilgi edinin.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: 6fa63cbe13fe98565ffb42b56f3ade86720cedb3
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275951"
---
# <a name="hartreefock-theory"></a>Hartree – Fock teorisi

Hisse kutları benzetiminde en önemli miktar, Hamiltonian matrisin en düşük enerji eigenvector değeri olan zemin durumudur.
Bunun nedeni, yeniden eylem oranları gibi oda sıcaklık miktarlarındaki en fazla molecules 'in, bir yeniden eylem yasındaki adımın başlangıcını ve bitişini betimleyen ve oda sıcaklığının genellikle orta eyalet olduğu durumlar arasındaki ücretsiz enerji farklılıklarıyla eşit olduğu durumdur.
Baş durum, genellikle daha fazla bilgi almak için çok zor olsa da (hisse bir bilgisayar ile bile), katlanarak çok sayıda yapılandırma üzerinden bir dağıtım olduğundan.
Zemin eyalet enerji gibi miktarlar öğrenilebilir.
Örneğin, $ \ket{\psı} $ herhangi bir saf hisse durumundaysa, \begin{Equation} E = \bra{\psı} \hat{H} \ket{\psı} \end{Equation}, sistemin o durumda sahip olduğu ortalama enerji sağlar.
Bu durumda, bu değer en küçük değeri veren durumdur. Sonuç olarak, doğru zemin durumu için mümkün olduğunca yakın olan bir durumun seçilmesi, doğrudan enerjiyi tahmin etmek için (değişen bir sanal bölge kapsamında olduğu gibi) ya da aşama tahmini aracılığıyla önemli bir durum seçmektir.

Hartree – Fock teorik, hisse sistemleri için ilk durumu oluşturmak için basit bir yol sağlar. Bir hisse sisteminin zemin durumu için tek bir sdaha daha sonra determinantı verir. Bu uçta, boşluk enerji alanını en aza indiren, Fock-Space içinde bir döndürme bulur. Özellikle, $N $ Elektriklerde bir sistem için yöntem, < Begin{Equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j {0} \tus\mapsto \ Prod_ {j = 0} ^ değerini gerçekleştirir {N-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \demet {0} \defeq\ Prod_ {j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j {0} \tus, \end{Equation} bir anti-hermitian (ör. $u =-u ^ \hanger $) matris $u = \ sum_ {pq} u_ {PQ} a ^ \ dagger_p A_Q $. $U $ matrisinin orbilaçlerini ve $ \widetilde{a} ^ \ dagger_j $ ve $ \widetilde{a} _j $ ' ın oluşturma ve annimilasyon işleçlerini temsil ettiğinden, mumların yarsalları, deniz CK molesel döndürme-Orbitals gibi bir değere dikkat edilmelidir.


$U $ matrisi, daha sonra beklenen enerji $ \bra {0} \ Prod_ {j = 0} ^ {n-1} \widetilde{a} \_ j H \ prod \_ {k = 0} ^ {n-1} \widetilde{a} ^ \ dagger_k \tus$ değerini en iyi duruma getirdi {0} . Bu iyileştirme sorunları genel olarak oldukça zor olabilir; böylece, Hartree – Fock algoritması en iyi duruma getirme sorununa hızlı bir şekilde yakınsama eğilimi yaparak, özellikle de eşitlenmiş-Shell molecuları için daha yakın bir çözüm sağlar. Bu durumları nesnenin bir örneği olarak belirteceğiz `FermionWavefunction` . Örneğin, $a ^ \ dagger_ a ^ \ {1} dagger_ a ^ \ {2} dagger_ {6} {0} \tus$, aşağıdaki gibi kimya kitaplığında örneği oluşturulur.
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
Ayrıca, dizin ile Wave işlevlerinin dizinini oluşturabilir `SpinOrbital` ve ardından bu dizinleri tamsayılara aşağıdaki şekilde dönüştürebilirsiniz.
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

Hartree-Fock durumu ayrıca bir ile aşağıdaki şekilde yeniden oluşturulabilir `FermionHamiltonian` .
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

Bununla birlikte, özellikle de kesin bağıntılı sistemler için doğru sonuçlar elde etmek, Hartatin teorik, çok fazla
