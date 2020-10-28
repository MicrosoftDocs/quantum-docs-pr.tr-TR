---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: PrepareEntangledState işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 299d586f7581acdecf22da2f6bbfbb8d45f372f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732175"
---
# <a name="prepareentangledstate-operation"></a><span data-ttu-id="47677-102">PrepareEntangledState işlemi</span><span class="sxs-lookup"><span data-stu-id="47677-102">PrepareEntangledState operation</span></span>

<span data-ttu-id="47677-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="47677-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="47677-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="47677-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="47677-105">İkili entangles iki qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="47677-105">Pairwise entangles two qubit registers.</span></span>

<span data-ttu-id="47677-106">Diğer bir deyişle, iki kayıt söz konusu olduğunda, {1} {2} {00} {11} her kaydın $ \ket{0\cnoktalar 0} $ durumunda başlayacağını varsayarak, her bir kasadaki her bir qubit çifti arasında en yüksek düzeyde entangled State $ \frac {\sqrt} \left (\ment + \ket \ right) $ değerini hazırlar.</span><span class="sxs-lookup"><span data-stu-id="47677-106">That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.</span></span>

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="47677-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="47677-107">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="47677-108">Sol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="47677-108">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="47677-109">$ \Ket{0\cnoktalar 0} $ durumundaki qubit dizisi</span><span class="sxs-lookup"><span data-stu-id="47677-109">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="47677-110">right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="47677-110">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="47677-111">$ \Ket{0\cnoktalar 0} $ durumundaki qubit dizisi</span><span class="sxs-lookup"><span data-stu-id="47677-111">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="47677-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47677-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

