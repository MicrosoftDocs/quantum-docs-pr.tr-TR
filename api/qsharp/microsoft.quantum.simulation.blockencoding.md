---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: Kullanıcı tanımlı tür Blockenkodlama
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 75fdbf13cf07d906982d4a611d1d25b3e29db2cd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225440"
---
# <a name="blockencoding-user-defined-type"></a>Kullanıcı tanımlı tür Blockenkodlama

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rastgele bir ilgilendiğiniz işlecin üst sol blokta kodlandığı bir Unitary temsil eder.

Diğer bir deyişle,, `BlockEncoding` Sistem kaydı üzerinde işlem yapan, $H bir ilgi alanının rastgele işleci olan bir Unitary $U $, `s` yardımcı durum $ \ayraç _a $ ' ne karşılık gelen sol üst blokta kodlanır {0} . Yani

$ $ \begin{hizalaması} (\bra {0} _a \otimes I_s) U (\ayraç {0} _a \otimes I_s) = H \end{hizalaması} $ $.

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

