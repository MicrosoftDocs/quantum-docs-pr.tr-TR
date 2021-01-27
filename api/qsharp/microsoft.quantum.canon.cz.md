---
uid: Microsoft.Quantum.Canon.CZ
title: CZ işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: cef1544fb76d561cfd0949c84c487550d523bb85
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840698"
---
# <a name="cz-operation"></a><span data-ttu-id="a4860-102">CZ işlemi</span><span class="sxs-lookup"><span data-stu-id="a4860-102">CZ operation</span></span>

<span data-ttu-id="a4860-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a4860-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a4860-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a4860-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a4860-105">Denetlenen-Z (CZ) kapısını bir qubit çiftiyle uygular.</span><span class="sxs-lookup"><span data-stu-id="a4860-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="a4860-106">$ $ \begin{hizalaması} 1 & 0 & 0 & 0 0 \\ \\ & 1 & 0 & 0 0 & 0 & \\ \\ 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{hizalaması}, $ $ burada satırlar ve sütunlar, hisse kavramları kılavuzunda olduğu gibi düzenlenmiştir.</span><span class="sxs-lookup"><span data-stu-id="a4860-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a4860-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="a4860-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="a4860-108">Denetim: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a4860-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a4860-109">CZ kapısı için denetim qubit.</span><span class="sxs-lookup"><span data-stu-id="a4860-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a4860-110">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a4860-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a4860-111">CZ kapısı için hedef qubit.</span><span class="sxs-lookup"><span data-stu-id="a4860-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a4860-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a4860-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a4860-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a4860-113">Remarks</span></span>

<span data-ttu-id="a4860-114">Eşdeğer:</span><span class="sxs-lookup"><span data-stu-id="a4860-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```