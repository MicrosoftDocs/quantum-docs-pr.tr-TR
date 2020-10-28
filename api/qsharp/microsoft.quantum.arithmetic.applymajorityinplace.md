---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: Applymajorityınplace işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 3664ffe96cd1db8cf5e8898387fe7f2d45b4ea98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731834"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="b58a7-102">Applymajorityınplace işlemi</span><span class="sxs-lookup"><span data-stu-id="b58a7-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="b58a7-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b58a7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b58a7-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b58a7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b58a7-105">Qubits 'in bir kaydındaki üç qubit çoğunluk işlemini yerinde uygular.</span><span class="sxs-lookup"><span data-stu-id="b58a7-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit
```


## <a name="description"></a><span data-ttu-id="b58a7-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b58a7-106">Description</span></span>

<span data-ttu-id="b58a7-107">Bu işlem çoğunluk fonksiyonunu 3 qubit üzerinde yerinde hesaplar.</span><span class="sxs-lookup"><span data-stu-id="b58a7-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="b58a7-108">Çıkış qubit $z $ ve giriş qubitleri $x $ ve $y $ olarak belirtirseniz, işlem şu dönüşümü gerçekleştirir: $ \ket{xyz} \sağtarrow \ket{x \oplus z} \ket{y \ OPLUS z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="b58a7-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="b58a7-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="b58a7-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="b58a7-110">Çıkış: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b58a7-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b58a7-111">İlk giriş qubit.</span><span class="sxs-lookup"><span data-stu-id="b58a7-111">First input qubit.</span></span> <span data-ttu-id="b58a7-112">Çıktının yerinde hesaplandığına ve bu qubit 'de depolandığını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="b58a7-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="b58a7-113">Giriş: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b58a7-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b58a7-114">İkinci ve üçüncü giriş qubit.</span><span class="sxs-lookup"><span data-stu-id="b58a7-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b58a7-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b58a7-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

