---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: PrepareEntangledState işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 5f6e3ea1e7638d3bc446f21ace2968cf8284353a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210480"
---
# <a name="prepareentangledstate-operation"></a><span data-ttu-id="b15f6-102">PrepareEntangledState işlemi</span><span class="sxs-lookup"><span data-stu-id="b15f6-102">PrepareEntangledState operation</span></span>

<span data-ttu-id="b15f6-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="b15f6-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="b15f6-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b15f6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b15f6-105">İkili entangles iki qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="b15f6-105">Pairwise entangles two qubit registers.</span></span>

<span data-ttu-id="b15f6-106">Diğer bir deyişle, iki kayıt söz konusu olduğunda, {1} {2} {00} {11} her kaydın $ \ket{0\cnoktalar 0} $ durumunda başlayacağını varsayarak, her bir kasadaki her bir qubit çifti arasında en yüksek düzeyde entangled State $ \frac {\sqrt} \left (\ment + \ket \ right) $ değerini hazırlar.</span><span class="sxs-lookup"><span data-stu-id="b15f6-106">That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.</span></span>

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b15f6-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="b15f6-107">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="b15f6-108">Sol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b15f6-108">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b15f6-109">$ \Ket{0\cnoktalar 0} $ durumundaki qubit dizisi</span><span class="sxs-lookup"><span data-stu-id="b15f6-109">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="b15f6-110">right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b15f6-110">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b15f6-111">$ \Ket{0\cnoktalar 0} $ durumundaki qubit dizisi</span><span class="sxs-lookup"><span data-stu-id="b15f6-111">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="b15f6-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b15f6-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

