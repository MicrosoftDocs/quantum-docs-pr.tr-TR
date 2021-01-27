---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: Nicetumromqubitcount işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: d6eac64eb62ec7a88d3231249b0bb1e05818f6e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856806"
---
# <a name="quantumromqubitcount-function"></a>Nicetumromqubitcount işlevi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> Miktar Tumromqubitcount kullanım dışı bırakıldı. Lütfen <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> bunun yerine kullanın.

Tarafından döndürülen işleme ayrılması gereken qubits sayısının toplam sayısını döndürür `QuantumROM` .

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a>Giriş

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

Hedef hata $ \ Epsilon $.


### <a name="ncoeffs--int"></a>nCoeffs: [Int](xref:microsoft.quantum.lang-ref.int)

İçinde belirtilen katsayının sayısı `QuantumROM` .



## <a name="output--intintint"></a>Çıkış: ([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)))

## <a name="first-parameter"></a>İlk parametre

`(x,(y,z))` `x = y + z` Ayrılan toplam qubit sayısı, `y` yazmaç için qubit sayısı `LittleEndian` ve `z` çöp qubit sayısı olan bir kayıt düzeni.