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
# <a name="blockencoding-user-defined-type"></a><span data-ttu-id="ffb99-102">Kullanıcı tanımlı tür Blockenkodlama</span><span class="sxs-lookup"><span data-stu-id="ffb99-102">BlockEncoding user defined type</span></span>

<span data-ttu-id="ffb99-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ffb99-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ffb99-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ffb99-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ffb99-105">Rastgele bir ilgilendiğiniz işlecin üst sol blokta kodlandığı bir Unitary temsil eder.</span><span class="sxs-lookup"><span data-stu-id="ffb99-105">Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.</span></span>

<span data-ttu-id="ffb99-106">Diğer bir deyişle,, `BlockEncoding` Sistem kaydı üzerinde işlem yapan, $H bir ilgi alanının rastgele işleci olan bir Unitary $U $, `s` yardımcı durum $ \ayraç _a $ ' ne karşılık gelen sol üst blokta kodlanır {0} .</span><span class="sxs-lookup"><span data-stu-id="ffb99-106">That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="ffb99-107">Yani</span><span class="sxs-lookup"><span data-stu-id="ffb99-107">That is,</span></span>

<span data-ttu-id="ffb99-108">$ $ \begin{hizalaması} (\bra {0} _a \otimes I_s) U (\ayraç {0} _a \otimes I_s) = H \end{hizalaması} $ $.</span><span class="sxs-lookup"><span data-stu-id="ffb99-108">$$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.</span></span>

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

