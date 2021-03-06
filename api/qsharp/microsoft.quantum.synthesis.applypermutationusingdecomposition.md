---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: Applyperdeğiştirici Tionusingayrıştırma işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 765b6d301363021f5b57a22f90e2ada38c9c09ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857387"
---
# <a name="applypermutationusingdecomposition-operation"></a>Applyperdeğiştirici Tionusingayrıştırma işlemi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir hisse cıklarca, ayrıştırma tabanlı senklerde bir PERMÜTASYONA göre rekabet eden bir değer sağlar.

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Bu yordam, ayrıştırma tabanlı sensıs yaklaşımını uygular.  Giriş, \{ \} bir $n $-değişken ters çevrilebilir Boole işlevini temsil eden, $2 ^ n $ öğe $0, \ noktalar, 2 ^ n-1 $ üzerinden bir permütasyon $ \pı $.
Algoritma yinelenen her bir dizin $i $ için aşağıdaki adımları gerçekleştirir:

1. İşlem $ ((\ pi_l, \ pi_r), \pı ') $, $ \ pi_l $ ve $ \ pi_r $ görüntülerinin öğelerinde, $i $ ve $ \pi ' $ görüntüleri dışındaki dizinlerde bulunan öğelerinde bitleri değiştirmez ve öğelerinde bit $i $ değerini değiştirmeyin.
2. $ \Pı \leftarrow \pı ' $ değerini ayarlayın ve sabit noktalı olmayan öğelere bağlı olarak $ \ pi_l $ ve $ \ pi_r $ adresinden Truth tabloları türetirsiniz.

Tüm değişken dizinleri için bu adımları uyguladıktan sonra, kalan permütasyon $ \pı $ kimlik olur ve toplanan Truth tablolarına ve dizinlerine göre, bir tane, işlemi kullanarak Truth tablo denetimli @"microsoft.quantum.intrinsic.x" işlemler uygulayabilir @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" .

Değişken sırası $0, \noktalar, n-$1 şeklindedir.  İşlemde özel bir değişken sırası belirtilebilir @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .

## <a name="input"></a>Giriş

### <a name="perm--int"></a>izin: [Int](xref:microsoft.quantum.lang-ref.int)[]

0 ' dan başlayarak $2 ^ n $ öğe için bir permütasyon.


### <a name="qubits--littleendian"></a>qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Permütasyonun uygulandığı $n $ qubits listesi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Örnek

Bir işlemi sentezleştirmek için `SWAP` :

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecomposition([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a>Başvurular

- [*Alexde Vos*, *Yıvan Van Renterged*, ADV. comm. 2 (2), 2008, PP. 183--200](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [*Mathias Soeken*, *gamze Tag*, *Gerhard W. Dueck*, *Rolf Drechsler*, sembolik hesaplama 73 (2016), PP. 1--26](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Sensıs. Applyperdeğiştirici Tionusingdekompozisyontionwithvariableorder](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [Microsoft. hisse. Sensıs. Applyperdeğiştirici Tionusingtransformation](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)