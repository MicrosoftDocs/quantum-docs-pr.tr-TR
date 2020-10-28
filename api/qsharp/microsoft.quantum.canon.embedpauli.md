---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: c78406aa4557834ac2bb40cf1847696d075e5135
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728712"
---
# <a name="embedpauli-function"></a><span data-ttu-id="1bffb-102">EmbedPauli işlevi</span><span class="sxs-lookup"><span data-stu-id="1bffb-102">EmbedPauli function</span></span>

<span data-ttu-id="1bffb-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1bffb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1bffb-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1bffb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1bffb-105">Bir tek qubit Pauli operatörü ve bir qubit dizini verildiğinde, bu dizinde ve diğer her dizinde verilen tek qubit işleciyle bir multi-qubit Pauli işleci döndürür `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="1bffb-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="1bffb-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1bffb-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="1bffb-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="1bffb-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="1bffb-108">Verilen konuma yerleştirilecek tek qubit Pauli işleci.</span><span class="sxs-lookup"><span data-stu-id="1bffb-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="1bffb-109">Konum: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1bffb-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1bffb-110">`output[location] == pauli`Bu işlevin çıktısı olduğu gibi bir dizin `output` .</span><span class="sxs-lookup"><span data-stu-id="1bffb-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="1bffb-111">n: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1bffb-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1bffb-112">Döndürülecek dizinin uzunluğu.</span><span class="sxs-lookup"><span data-stu-id="1bffb-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="1bffb-113">Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="1bffb-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

