---
title: Ürdün-Wigner temsili | Microsoft Docs
description: Ürdün-Wigner gösterimi kavramsal belgeler
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
ms.openlocfilehash: f34233bc17ff68a9e04256959f8d79be2682c34f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184058"
---
# <a name="jordan-wigner-representation"></a>Ürdün-Wigner temsili

İkinci quantiilaHamiltonians, $a ^ \dağılım $ (oluşturma) ve $a $ (annıılasyon) bakımından kolayca temsil edilirken, bu işlemler hisse bilgisayarları 'nda temel işlemler değildir.
Sonuç olarak, bunları bir hisse bir bilgisayar için uygulamak istiyoruz, işleçleri bir hisse bilgisayar üzerinde uygulanabilen Unitary matrisleriyle eşleştirmemiz gerekir.
Ürdün – Wigner temsili bir eşleme sağlar.
Ancak, Bravyi – Kitaev temsili gibi diğerleri de mevcuttur ve kendi göreli avantajları ve dezavantajları vardır.
Ürdün-Wigner gösteriminin ana avantajı basittür.

Ürdün-Wigner temsili türetmek için doğrudan ileri sarma.
Bir State $ \ket{0}_j $ 'ın, döndürme ORBIT $j $ 'ın boş olduğunu ve $ \ket{1}_j $ 'ın dolu olduğunu gösterir.
Bu, qubits 'in belirli bir dönüş orbisi 'nin mesleklerinden doğal olarak depolayabileceği anlamına gelir.
Daha sonra bu $a ^ \abger_j \ ayraç{0}_j = \ket{1}_j $ ve $a ^ \abger_j \ demet{1}_j = $0.
\Begin{hizalaması} a ^ \abger_j & = \begin{bmatrix}0 & 1 \\\ 0 & 0 \end{bmatrix} = \frac{X_j + iY_j}{2}, \tımumarası\\\\ a_j & = \begin{bmatrix}0 & 0 \\\ 1 & 0 \end{ bmatrix} = \frac{X_j-iY_j}{2}, \end{hizalaması}; burada $X _j $ ve $Y _j $, qubit $Y $ üzerinde davranan Pauli-$X $ ve-$j $ işleçleridir.
Bu, tek bir dönüş için, aylık bilgisayarlarda anlamış olan Unitary matrislerinin yanı sıra oluşturma ve Annme işleçlerini temsil etmek için çok kolay olduğunu gösterir.
$X $ ve $Y $ 'nin Unitary $a ^ \hanger $ ve $a $ olduğunu unutmayın.
Daha sonra bunun simülasyonu için bir zorluk oluşturmadığından daha sonra görülecektir.

Kalan tek bir sorun, yukarıdaki oluşturma tek bir değer değiştirici için çalıştığından, iki veya daha fazla döndürme veya daha fazla değer içeren sistemlerde başarısız olmasına neden olur.
Fermıons antisymmetic olduğundan, tüm $j $ ve $k $ için ^ \abger_j a ^ \abger_k =-a ^ \abger_k a ^ \abger_j $ $a olduğunu biliyoruz.
Ancak, $ $ \left (\frac{X_j-iY_j}{2}\ right) \left (\frac{X_k-iY_k}{2}\right) = \left (\frac{X_k-iY_k}{2}\right) \left (\frac{X_j-iY_j}{2}\ right).
$ $ Diğer bir deyişle, iki oluşturma işleci gereken şekilde koruma altına mazlar.
Bu, daha zarif bir biçimde daha basit bir şekilde giderilebilir.
Bu, Pauli işleçlerini doğal olarak anti-commute öğesine göz önünde bir şekilde çözmedir.
Özellikle, $XZ =-ZX $ ve $YZ =-ZY $.
Bu nedenle, $Z $ işleçlerini işlecin yapılanından yararlanarak, doğru anti-commutation benzetimi yapabilir.
Tam oluşturma işlemi aşağıdaki gibidir: 

\begin{hizalaması} a ^ \gesger_1 & = \left (\frac{X-iY}{2}\ right) \otimes 1 \otimes 1 \otimes 1\\\\ a ^ \dagger_2 & = Z\otimes\left (\frac{X-iY}{2}\ sağ) \otimes 1 \ otimes 1 \otimes \cnoktalar \otimes 1\\\\ a ^ \abger_3 & = Z\otimes \left (\frac{X-iY}{2}\right) \otimes 1 \otimes \cnoktalara\\\\ & \vnoktalar\\\\ a ^ \Abger_n & = Z\otimes Z\otimes Z\otimes Z \otimes \cnoktalar \otimes Z\otimes \left (\frac{X-iY}{2}\ right). \label{EQ: JW} \end{hizalaması}

Pauli işleçleri açısından, $n _j $ sayı işleçlerini ifade etmek de kullanışlıdır.
Ktam, $Z $ işleçlerinin dizeleri (Ürdün-Wigner dizeleri olarak bilinir), bu değişikliği yaptıktan sonra iptal eder.
Bunu yaptıktan sonra (ve bu $X _Ji_j = iZ_j $), \begin{Equation} n_j = a ^ \abger_j a_j = \frac{(1-Z_j)}{2}.
\end{Equation}


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a>Ürdün-Wigner gösteriminde Hamiltonians oluşturuluyor

Ürdün-Wigner gösterimini çağırdıktan sonra Hamiltonian 'yi Pauli işleçleri toplamına çevirmek, düz bir işlemdir.
Tek bir, Fermıonic Hamiltonian içindeki her bir $a ^ \dağılım $ ve $a $ işleçlerinin her birini yukarıda verilen Pauli-Operators dizeleriyle değiştirmek yeterlidir.
Bu değişimi gerçekleştirdiğinde, Hamiltonian içinde yalnızca beş terim sınıfı vardır.
Bu beş sınıf, tek gövdedeki ve Hamiltonian 'daki iki gövdede bulunan $p, q $ ve $p, q, r, s $ farklı yollarla ilgilidir.
Bu beş sınıf, $p > q > r > s $ ve gerçek değerli Orbitals gibi durumlar için

\begin{hizalaması} h_ {PP} a_p ^ \hanger a_p & = \sum_p \frac{h_{PP}}{2}(1-Z_p)\\\\ h_ {PQ} (a_p ^ \dağılım A_Q + a ^ \hanger_q a_p) & = \frac{h_{PQ}}{2}\left (\prod_{j = q + 1} ^ {p-1} Z_j \ right) \ Sol (X_pX_q + Y_pY_q\right)\\\\ h_ {pqqp} n_p n_q & = \frac{h_{pqqp}}{4}\left (1-Z_p-Z_q + Z_pZ_q \ right)\\\\ h_ {pqqr} & = \frac{h_{pqqr}}{2}\left (\prod_{j = r + 1} ^ {p-1} Z_j \right) \left (X_pX_r + Y_pY_r\right) \left (\frac{1-Z_q}{2}\ right)\\\\ h_ {pqrs} & = \frac{h_{pqrs}}{8}\prod_{j = s + 1} ^ {r-1} Z_j\prod_ {k = q + 1} ^ {p-1} Z_k \Big (XXXX-XXYY + Xyxy\noumarası\\\\ & \qquad\qquad\qquad\qquad\qdörtlü + YıXXY + YXYX-YYXX\nonumber\\\\ & \qquad\qquad\qquad\qquad\qdörtlü + XYYX + YYYY\Big) \end{hizalaması}

Bu Hamiltonians by el ile yalnızca bu değiştirme kurallarının uygulanmasını gerektirirken, bunun yapılması milyonlarca Hafretonian terimlerinden oluşabilen büyük motacules için uygun olmayabilir.
Alternatif olarak, Hamiltonian 'nin `FermionHamiltonian` temsili verilen `JordanWignerEncoding` otomatik olarak oluşturacağız.

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
