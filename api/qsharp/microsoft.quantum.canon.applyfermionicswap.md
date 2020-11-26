---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Applyfermıonicswap işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 0c470705843a6360df0a72374570d86571397e41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218810"
---
# <a name="applyfermionicswap-operation"></a>Applyfermıonicswap işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fermıonic SWAP 'ı uygular.

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

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