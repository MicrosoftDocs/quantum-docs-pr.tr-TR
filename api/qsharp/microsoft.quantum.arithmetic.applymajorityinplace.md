---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: Applymajorityınplace işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: c32d7546fb753f78a72479cec11a6ed09c5e6179
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190743"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="2b33f-102">Applymajorityınplace işlemi</span><span class="sxs-lookup"><span data-stu-id="2b33f-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="2b33f-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2b33f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2b33f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2b33f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2b33f-105">Qubits 'in bir kaydındaki üç qubit çoğunluk işlemini yerinde uygular.</span><span class="sxs-lookup"><span data-stu-id="2b33f-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="2b33f-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="2b33f-106">Description</span></span>

<span data-ttu-id="2b33f-107">Bu işlem çoğunluk fonksiyonunu 3 qubit üzerinde yerinde hesaplar.</span><span class="sxs-lookup"><span data-stu-id="2b33f-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="2b33f-108">Çıkış qubit $z $ ve giriş qubitleri $x $ ve $y $ olarak belirtirseniz, işlem şu dönüşümü gerçekleştirir: $ \ket{xyz} \sağtarrow \ket{x \oplus z} \ket{y \ OPLUS z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="2b33f-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="2b33f-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="2b33f-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="2b33f-110">Çıkış: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2b33f-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2b33f-111">İlk giriş qubit.</span><span class="sxs-lookup"><span data-stu-id="2b33f-111">First input qubit.</span></span> <span data-ttu-id="2b33f-112">Çıktının yerinde hesaplandığına ve bu qubit 'de depolandığını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="2b33f-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="2b33f-113">Giriş: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2b33f-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2b33f-114">İkinci ve üçüncü giriş qubit.</span><span class="sxs-lookup"><span data-stu-id="2b33f-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2b33f-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b33f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

