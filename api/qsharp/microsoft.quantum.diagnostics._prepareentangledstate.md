---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 97a55b4bb85095c7d8e8432dfcd1c6d6f7e93cdc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223944"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="c51d7-102">_prepareEntangledState işlemi</span><span class="sxs-lookup"><span data-stu-id="c51d7-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="c51d7-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c51d7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c51d7-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c51d7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c51d7-105">İki kayıt verildiğinde, ilgili yazmaçlardaki her bir qubit çifti arasında en yüksek düzeyde bir durum hazırlar.</span><span class="sxs-lookup"><span data-stu-id="c51d7-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="c51d7-106">Tüm qubits, | 0 ⟩ durumunda başlamalıdır.</span><span class="sxs-lookup"><span data-stu-id="c51d7-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="c51d7-107">Sonuç olarak her bir kayıttaki karşılık gelen qubit çiftleri $ \bra{\ beta_ {00} } \ket{\ beta_ {00} } $ içinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="c51d7-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c51d7-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="c51d7-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="c51d7-109">Sol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c51d7-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c51d7-110">$ \Ket{0\cnoktalar 0} $ durumundaki qubit dizisi</span><span class="sxs-lookup"><span data-stu-id="c51d7-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="c51d7-111">right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c51d7-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c51d7-112">$ \Ket{0\cnoktalar 0} $ durumundaki qubit dizisi</span><span class="sxs-lookup"><span data-stu-id="c51d7-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="c51d7-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c51d7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

