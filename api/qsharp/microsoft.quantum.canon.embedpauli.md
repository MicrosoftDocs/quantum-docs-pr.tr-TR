---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: 0e6a93e22ee495abcc44bdf522e7c72c0981308b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840527"
---
# <a name="embedpauli-function"></a><span data-ttu-id="b04df-102">EmbedPauli işlevi</span><span class="sxs-lookup"><span data-stu-id="b04df-102">EmbedPauli function</span></span>

<span data-ttu-id="b04df-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b04df-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b04df-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b04df-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b04df-105">Bir tek qubit Pauli operatörü ve bir qubit dizini verildiğinde, bu dizinde ve diğer her dizinde verilen tek qubit işleciyle bir multi-qubit Pauli işleci döndürür `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="b04df-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="b04df-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="b04df-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="b04df-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="b04df-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="b04df-108">Verilen konuma yerleştirilecek tek qubit Pauli işleci.</span><span class="sxs-lookup"><span data-stu-id="b04df-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="b04df-109">Konum: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b04df-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b04df-110">`output[location] == pauli`Bu işlevin çıktısı olduğu gibi bir dizin `output` .</span><span class="sxs-lookup"><span data-stu-id="b04df-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="b04df-111">n: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b04df-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b04df-112">Döndürülecek dizinin uzunluğu.</span><span class="sxs-lookup"><span data-stu-id="b04df-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="b04df-113">Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="b04df-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="example"></a><span data-ttu-id="b04df-114">Örnek</span><span class="sxs-lookup"><span data-stu-id="b04df-114">Example</span></span>

<span data-ttu-id="b04df-115">Diziyi almak için `[PauliI, PauliI, PauliX, PauliI]` :</span><span class="sxs-lookup"><span data-stu-id="b04df-115">To obtain the array `[PauliI, PauliI, PauliX, PauliI]`:</span></span>

```qsharp
EmbedPauli(PauliX, 2, 3);
```