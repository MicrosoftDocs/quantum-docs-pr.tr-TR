---
title: Ürdün-Wigner temsili
description: Hamiltonian işleçlerini, bir hisse bilgisayarında daha kolay bir şekilde uygulanabilen Unitary matrisleriyle eşleyen Ürdün-Wigner gösterimi hakkında bilgi edinin.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
no-loc:
- Q#
- $$v
ms.openlocfilehash: 29abb4d2ef11239a58af45bc4eee3bd60d20a6c7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833846"
---
# <a name="jordan-wigner-representation"></a>Ürdün-Wigner temsili

İkinci quantiilaHamiltonians, $a ^ \dağılım $ (oluşturma) ve $a $ (annıılasyon) bakımından kolayca temsil edilirken, bu işlemler hisse bilgisayarları 'nda temel işlemler değildir.
Sonuç olarak, bunları bir hisse bir bilgisayar için uygulamak istiyoruz, işleçleri bir hisse bilgisayar üzerinde uygulanabilen Unitary matrisleriyle eşleştirmemiz gerekir.
Ürdün – Wigner temsili bir eşleme sağlar.
Ancak, Bravyi – Kitaev temsili gibi diğerleri de mevcuttur ve kendi göreli avantajları ve dezavantajları vardır.
Ürdün-Wigner gösteriminin ana avantajı basittür.

Ürdün-Wigner temsili türetmek için doğrudan ileri sarma.
Bir State $ \ket {0} _j $ 'ın, döndürme ORBIT $j $ 'ın boş olduğunu ve $ \ket {1} _j $ 'ın dolu olduğunu gösterir.
Bu, qubits 'in belirli bir dönüş orbisi 'nin mesleklerinden doğal olarak depolayabileceği anlamına gelir.
Daha sonra bu $a ^ \ dagger_j {0} \tus_j = \ket {1} _j $ ve $a ^ \ dagger_j \demet {1} _j = $0.
\Begin{hizalaması} a ^ \ dagger_j &= \begin{bmatrix}0 & 0 \\ \ 1 &0 \ End{bmatrix} = \frac{X_j-iY_j} {2} , \no \\ \\ a_j &= \begin{bmatrix}0 & 1 \\ \ 0 &0 \end{bmatrix} = \frac{X_j + iY_j} {2} , \end{hizalaması}; burada $X _j $ ve $Y _j $, qubit $X $ üzerinde davranan Pauli-$Y $ ve-$j $ işleçleridir.

>[!NOTE]
> Q#$ \Ket {0} $ durumu, $Z $ işlecinin + 1 eigenstate değerini temsil eder. Fizik $ \ demet $ ' in bazı alanlarında {0} düşük enerji zemin durumu ve bu nedenle $Z $ işlecinin-1 eigenstate 'i temsil eder. Bu nedenle, bazı formüller popüler belgeler farklılık gösterebilir.

Kimya kitaplığında, {0} dolu olmayan bir döndürme-orbçeyi göstermek için $ \ket $ kullanıyoruz.
Bu, tek bir dönüş için, aylık bilgisayarlarda anlamış olan Unitary matrislerinin yanı sıra oluşturma ve Annme işleçlerini temsil etmek için çok kolay olduğunu gösterir.
$X $ ve $Y $ 'nin Unitary $a ^ \hanger $ ve $a $ olduğunu unutmayın.
Daha sonra bunun simülasyonu için bir zorluk oluşturmadığından daha sonra görülecektir.

Kalan tek bir sorun, yukarıdaki oluşturma tek bir değer değiştirici için çalıştığından, iki veya daha fazla döndürme veya daha fazla değer içeren sistemlerde başarısız olmasına neden olur.
Fermıons antisymmetic olduğundan, tüm dagger_j $ ve $j $ için ^ \ dagger_k =-a ^ \ dagger_k a ^ \ $k $ dagger_j $a olduğunu biliyoruz.
Ancak, $ $ \left (\frac{X_j-iY_j} {2} \right) \left (\frac{X_k-iY_k} {2} \right) = \left (\frac{X_k-iY_k} \right {2} ) \left (\frac{X_j-iY_j} {2} \right).
$ $ Diğer bir deyişle, iki oluşturma işleci gereken şekilde koruma altına mazlar.
Bu, daha zarif bir biçimde daha basit bir şekilde giderilebilir.
Bu, Pauli işleçlerini doğal olarak anti-commute öğesine göz önünde bir şekilde çözmedir.
Özellikle, $XZ =-ZX $ ve $YZ =-ZY $.
Bu nedenle, $Z $ işleçlerini işlecin yapılanından yararlanarak, doğru anti-commutation benzetimi yapabilir.
Tam oluşturma işlemi aşağıdaki gibidir: 

\begin{hizalaması} a ^ \ dagger_1 &= \left (\frac{X-iY} {2} \ sağ) \otimes 1 \otimes 1 \\ \\ bir ^ \ dagger_2 &= Z\otimes\left (\frac{X-iY} {2} \right) \otimes 1 \ otimes 1 \otimes \cnoktalar \otimes 1, bir \\ \\ ^ \ dagger_3 &= z\otimes z\otimes \Left (\frac{X-iY} \ {2} sağ) \otimes 1, \\ \\ \vnoktalara bir \\ \\ ^ \ dagger_N &= z\otimes z\otimes Z\otimes Z \otimes \cnoktalar \Otimes Z\otimes \left (\frac{x-iy} {2} \right). & \label{EQ: JW} \end{hizalaması}

Ayrıca, Pauli işleçleri açısından, $n _j $ sayı işleçlerini ifade etmek de kullanışlıdır.
Ktam, $Z $ işleçlerinin dizeleri (Ürdün-Wigner dizeleri olarak bilinir), bu değişikliği yaptıktan sonra iptal eder.
Bunu yaptıktan sonra (ve bu $X _jY_j = iZ_j $), \begin{Equation} n_j = a ^ \ dagger_j a_j = \frac{(1-Z_j)} {2} .
\end{Equation}


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a>Ürdün-Wigner gösteriminde Hamiltonians oluşturuluyor

Ürdün-Wigner gösterimini çağırdıktan sonra Hamiltonian 'yi Pauli işleçleri toplamına çevirmek, düz bir işlemdir.
Tek bir, Fermıonic Hamiltonian içindeki her bir $a ^ \dağılım $ ve $a $ işleçlerinin her birini yukarıda verilen Pauli-Operators dizeleriyle değiştirmek yeterlidir.
Bu değişimi gerçekleştirdiğinde, Hamiltonian içinde yalnızca beş terim sınıfı vardır.
Bu beş sınıf, tek gövdedeki ve Hamiltonian 'daki iki gövdede bulunan $p, q $ ve $p, q, r, s $ farklı yollarla ilgilidir.
Bu beş sınıf, $p>q>r>s $ ve gerçek değerli Orbitals gibi durumlar için

\begin{hizalaması} h_ {PP} a_p ^ \hanger a_p &= \ sum_p \frac{h_ {PP}} {2} (1-Z_p) \\ \\ h_ {PQ} (a_p ^ \dağılım A_Q + a ^ \ dagger_q a_p) &= \frac{h_ {PQ}} {2} \left (\ Prod_ {j = q + 1} ^ {p-1} Z_j \ sağa) \left (X_pX_q + Y_pY_q \ sağ) \\ \\ h_ {pqqp} n_p n_q &= \frac{h_ {pqqp}} {4} \left (1-Z_p-Z_q + Z_pZ_q \right) \\ \\ h_ {pqqr} &= \frac{h_ {pqqr}} {2} \left (\ Prod_ {j = r + 1} ^ {p-1} Z_j \ sağ) \left (X_pX_r + Y_pY_r \ sağ) \left (\frac{1-Z_q} {2} \right) \\ \\ h_ {pqrs} &= \frac{h_ {pqrs}} {8} \ Prod_ {j = s + 1} ^ {r-1} Z_j \ Prod_ {k = q + 1} ^ {p-1} Z_k \big (xxxx-xxyy + xyxy\qquad& \\ \\ \qquad\qquad\qquad\qquad\qdörtlü + ixxy + YXYX-YYXX\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qdörtlü + xyyx + yyyy\big) \end{hizalaması}

Bu Hamiltonians by el ile yalnızca bu değiştirme kurallarının uygulanmasını gerektirirken, bunun yapılması milyonlarca Hafretonian terimlerinden oluşabilen büyük motacules için uygun olmayabilir.
Alternatif olarak, `JordanWignerEncoding` `FermionHamiltonian` Hamiltonian 'nin verilen temsilini otomatik olarak oluşturarız.

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

Hamiltonians bu formda oluşturulduktan sonra, $e ^ {-iHt} $ tarafından oluşturulan dinamikleri bir dizi basit kapıya (bazı Kullanıcı tanımlanabilir hata toleransı) dizisine derlemek için hisse bir hisse simülasyonu algoritması kullanabilir.
Algoritmik belgelerindeki hisse simülasyonu, qubitişleştirme ve Trour – Suzuki formülleri için en popüler iki yöntemi tartıştık. Hamiltonian simülasyon kitaplığındaki her iki yöntem için de uygulamalar sunuyoruz.
