---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Applyfermıonicswap işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 334f407a32dabc8f4e0a1a29c8f06a1b9f40dc59
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845046"
---
# <a name="applyfermionicswap-operation"></a>Applyfermıonicswap işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fermıonic SWAP 'ı uygular.

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Bu aslında, her iki qubit de 1s ise-1 Genel aşamasını uygularken qubits 'i değiştirir. Orbitleri, simetrik olmayan bir şekilde korur.
Daha fazla bilgi edinmek için bkz. .

Bu işlem, Unitary işleci \ Begin{hizalaması} f_ {Swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 0 & 0 & \\ \\ 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix} tarafından temsil edilir.
\end{hizalaması}

## <a name="input"></a>Giriş

### <a name="qubit1--qubit"></a>qubit1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Takas edilecek ilk qubit.


### <a name="qubit2--qubit"></a>qubit2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Takas edilecek ikinci qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Başvurular

- [*Ryan Bebush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic kanal*, arxıv: 1706.00023](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Intrinsic. SWAP](xref:Microsoft.Quantum.Intrinsic.SWAP)