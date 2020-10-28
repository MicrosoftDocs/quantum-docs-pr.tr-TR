---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: Hazırlık eşitlenmiş bit işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 5f42bf26a8f9638ea88c035a18846050c3776b45
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732650"
---
# <a name="preparequbit-operation"></a><span data-ttu-id="b4d66-102">Hazırlık eşitlenmiş bit işlemi</span><span class="sxs-lookup"><span data-stu-id="b4d66-102">PrepareQubit operation</span></span>

<span data-ttu-id="b4d66-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="b4d66-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="b4d66-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b4d66-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b4d66-105">`Zero`Verilen Pauli işlecinin ıdgenstate ' i () ile bir qubit hazırlar.</span><span class="sxs-lookup"><span data-stu-id="b4d66-105">Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator.</span></span>
<span data-ttu-id="b4d66-106">Identity işleci verilirse, qubit, yüksek ölçüde karışık duruma hazırlanır.</span><span class="sxs-lookup"><span data-stu-id="b4d66-106">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

<span data-ttu-id="b4d66-107">Qubit başlangıçta $ \ket {0} $ durumundaysa, bu işlem belirli bir Pauli işlecinin $ + $1 eigenstate veya için `PauliI` (bkz.) yerine en düşük karma durumunda qubit 'i hazırlar (bkz <xref:microsoft.quantum.preparation.preparesinglequbitidentity> .).</span><span class="sxs-lookup"><span data-stu-id="b4d66-107">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="b4d66-108">Qubit $ \ket $ dışında bir durumdaysa {0} , bu işlem şu kapıları uygular: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ for `PauliZ` and for <xref:microsoft.quantum.preparation.preparesinglequbitidentity> `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="b4d66-108">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="b4d66-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="b4d66-109">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="b4d66-110">temel: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="b4d66-110">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="b4d66-111">Pauli işleci $P $.</span><span class="sxs-lookup"><span data-stu-id="b4d66-111">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="b4d66-112">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b4d66-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b4d66-113">Hazırlanmaya yönelik bir qubit.</span><span class="sxs-lookup"><span data-stu-id="b4d66-113">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b4d66-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b4d66-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

