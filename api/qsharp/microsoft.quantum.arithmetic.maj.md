---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: MAJ işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: c1801d1d7ed04ead11b672f24d44a94989cf8f1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731447"
---
# <a name="maj-operation"></a><span data-ttu-id="9ad8a-102">MAJ işlemi</span><span class="sxs-lookup"><span data-stu-id="9ad8a-102">MAJ operation</span></span>

<span data-ttu-id="9ad8a-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9ad8a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9ad8a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9ad8a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9ad8a-105">Bu, yerinde çoğunluk işlemini 3 qubit 'e uygular.</span><span class="sxs-lookup"><span data-stu-id="9ad8a-105">This applies the in-place majority operation to 3 qubits.</span></span>

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="9ad8a-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="9ad8a-106">Description</span></span>

<span data-ttu-id="9ad8a-107">Hedef qubit durumunu $ \ket{z} $ olarak belirtirseniz, ve giriş qubits 'in $ \ket{x} $ ve $ \ket{y} $ olarak giriş durumları, bu işlem şu dönüşümü gerçekleştirir: $ \ket{xyz} \estarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="9ad8a-107">If we denote the state of the target qubit as $\ket{z}$, and input states of the input qubits as $\ket{x}$ and $\ket{y}$, then this operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="9ad8a-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="9ad8a-108">Input</span></span>

### <a name="input0--qubit"></a><span data-ttu-id="9ad8a-109">input0: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9ad8a-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9ad8a-110">İlk giriş qubit.</span><span class="sxs-lookup"><span data-stu-id="9ad8a-110">The first input qubit.</span></span>


### <a name="input1--qubit"></a><span data-ttu-id="9ad8a-111">input1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9ad8a-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9ad8a-112">İkinci giriş qubit.</span><span class="sxs-lookup"><span data-stu-id="9ad8a-112">The second input qubit.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9ad8a-113">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9ad8a-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9ad8a-114">Çoğunluk işlevinin uygulanacağı bir qubit.</span><span class="sxs-lookup"><span data-stu-id="9ad8a-114">A qubit onto which the majority function will be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9ad8a-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ad8a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

