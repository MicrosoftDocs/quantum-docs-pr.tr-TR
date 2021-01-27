---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: Applymajorityınplace işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 10b512392b2098663c09b2e07a09c4025da90706
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843721"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="2d4ef-102">Applymajorityınplace işlemi</span><span class="sxs-lookup"><span data-stu-id="2d4ef-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="2d4ef-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2d4ef-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2d4ef-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2d4ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2d4ef-105">Qubits 'in bir kaydındaki üç qubit çoğunluk işlemini yerinde uygular.</span><span class="sxs-lookup"><span data-stu-id="2d4ef-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="2d4ef-106">Description</span><span class="sxs-lookup"><span data-stu-id="2d4ef-106">Description</span></span>

<span data-ttu-id="2d4ef-107">Bu işlem çoğunluk fonksiyonunu 3 qubit üzerinde yerinde hesaplar.</span><span class="sxs-lookup"><span data-stu-id="2d4ef-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="2d4ef-108">Çıkış qubit $z $ ve giriş qubitleri $x $ ve $y $ olarak belirtirseniz, işlem şu dönüşümü gerçekleştirir: $ \ket{xyz} \sağtarrow \ket{x \oplus z} \ket{y \ OPLUS z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="2d4ef-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="2d4ef-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="2d4ef-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="2d4ef-110">Çıkış: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2d4ef-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2d4ef-111">İlk giriş qubit.</span><span class="sxs-lookup"><span data-stu-id="2d4ef-111">First input qubit.</span></span> <span data-ttu-id="2d4ef-112">Çıktının yerinde hesaplandığına ve bu qubit 'de depolandığını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="2d4ef-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="2d4ef-113">Giriş: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2d4ef-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2d4ef-114">İkinci ve üçüncü giriş qubit.</span><span class="sxs-lookup"><span data-stu-id="2d4ef-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2d4ef-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2d4ef-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

