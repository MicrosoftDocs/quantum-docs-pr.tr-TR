---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 5a74978a536a92dafae0b532805bd8e8ae1c888e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830980"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="e8d05-102">_prepareEntangledState işlemi</span><span class="sxs-lookup"><span data-stu-id="e8d05-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="e8d05-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e8d05-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e8d05-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e8d05-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e8d05-105">İki kayıt verildiğinde, ilgili yazmaçlardaki her bir qubit çifti arasında en yüksek düzeyde bir durum hazırlar.</span><span class="sxs-lookup"><span data-stu-id="e8d05-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="e8d05-106">Tüm qubits, | 0 ⟩ durumunda başlamalıdır.</span><span class="sxs-lookup"><span data-stu-id="e8d05-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="e8d05-107">Sonuç olarak her bir kayıttaki karşılık gelen qubit çiftleri $ \bra{\ beta_ {00} } \ket{\ beta_ {00} } $ içinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="e8d05-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e8d05-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="e8d05-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="e8d05-109">Sol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e8d05-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e8d05-110">$ \Ket{0\cnoktalar 0} $ durumundaki qubit dizisi</span><span class="sxs-lookup"><span data-stu-id="e8d05-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="e8d05-111">right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e8d05-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e8d05-112">$ \Ket{0\cnoktalar 0} $ durumundaki qubit dizisi</span><span class="sxs-lookup"><span data-stu-id="e8d05-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="e8d05-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e8d05-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

