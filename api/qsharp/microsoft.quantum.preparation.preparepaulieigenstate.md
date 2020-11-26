---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: PreparePauliEigenstate işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: b24852bb3a455a9fe04b3535156d0c3dfb1a7d12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193701"
---
# <a name="preparepaulieigenstate-operation"></a><span data-ttu-id="dba51-102">PreparePauliEigenstate işlemi</span><span class="sxs-lookup"><span data-stu-id="dba51-102">PreparePauliEigenstate operation</span></span>

<span data-ttu-id="dba51-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="dba51-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="dba51-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dba51-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dba51-105">Verilen Pauli işlecinin pozitif eigenstate değeri için bir qubit hazırlar.</span><span class="sxs-lookup"><span data-stu-id="dba51-105">Prepares a qubit in the positive eigenstate of a given Pauli operator.</span></span>
<span data-ttu-id="dba51-106">Identity işleci verilirse, qubit, yüksek ölçüde karışık duruma hazırlanır.</span><span class="sxs-lookup"><span data-stu-id="dba51-106">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="dba51-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="dba51-107">Description</span></span>

<span data-ttu-id="dba51-108">Qubit başlangıçta $ \ket {0} $ durumundaysa, bu işlem belirli bir Pauli işlecinin $ + $1 eigenstate veya için `PauliI` (bkz.) yerine en düşük karma durumunda qubit 'i hazırlar (bkz <xref:microsoft.quantum.preparation.preparesinglequbitidentity> .).</span><span class="sxs-lookup"><span data-stu-id="dba51-108">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="dba51-109">Qubit $ \ket $ dışında bir durumdaysa {0} , bu işlem şu kapıları uygular: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ for `PauliZ` and for <xref:microsoft.quantum.preparation.preparesinglequbitidentity> `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="dba51-109">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

## <a name="input"></a><span data-ttu-id="dba51-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="dba51-110">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="dba51-111">temel: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="dba51-111">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="dba51-112">Pauli işleci $P $.</span><span class="sxs-lookup"><span data-stu-id="dba51-112">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="dba51-113">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dba51-113">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="dba51-114">Hazırlanmaya yönelik bir qubit.</span><span class="sxs-lookup"><span data-stu-id="dba51-114">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dba51-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dba51-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

