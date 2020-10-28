---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: Kullanıcı tanımlı tür Blockenkodlama
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 1b769c58fd23b4ebc9d779cec3c47d8275822e5a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732471"
---
# <a name="blockencoding-user-defined-type"></a>Kullanıcı tanımlı tür Blockenkodlama

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Leyebilir [](https://nuget.org/packages/)


Rastgele bir ilgilendiğiniz işlecin üst sol blokta kodlandığı bir Unitary temsil eder.

Diğer bir deyişle,, `BlockEncoding` Sistem kaydı üzerinde işlem yapan, $H bir ilgi alanının rastgele işleci olan bir Unitary $U $, `s` yardımcı durum $ \ayraç _a $ ' ne karşılık gelen sol üst blokta kodlanır {0} . Yani

$ $ \begin{hizalaması} (\bra {0} _a \otimes I_s) U (\ayraç {0} _a \otimes I_s) = H \end{hizalaması} $ $.

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

