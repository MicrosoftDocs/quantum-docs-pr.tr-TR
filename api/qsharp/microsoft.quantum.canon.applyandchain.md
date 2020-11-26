---
uid: Microsoft.Quantum.Canon.ApplyAndChain
title: Applyandzinciri işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAndChain
qsharp.summary: Computes a chain of AND gates
ms.openlocfilehash: c53bca6ecf964f4358b0a7ff1c61d4e8e195cd7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219371"
---
# <a name="applyandchain-operation"></a><span data-ttu-id="bd2b7-102">Applyandzinciri işlemi</span><span class="sxs-lookup"><span data-stu-id="bd2b7-102">ApplyAndChain operation</span></span>

<span data-ttu-id="bd2b7-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bd2b7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bd2b7-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd2b7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd2b7-105">VE kapıları zincirini hesaplar</span><span class="sxs-lookup"><span data-stu-id="bd2b7-105">Computes a chain of AND gates</span></span>

```qsharp
operation ApplyAndChain (auxRegister : Qubit[], ctrlRegister : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="bd2b7-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="bd2b7-106">Description</span></span>

<span data-ttu-id="bd2b7-107">Geçici sonuçları hesaplamak için yardımcı qubits açıkça belirtilmelidir.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-107">The auxiliary qubits to compute temporary results must be specified explicitly.</span></span>
<span data-ttu-id="bd2b7-108">Bu kaydın uzunluğu `Length(ctrlRegister) - 2` , en az iki denetim varsa, aksi takdirde Uzunluk 0 ' dır.</span><span class="sxs-lookup"><span data-stu-id="bd2b7-108">The length of that register is `Length(ctrlRegister) - 2`, if there are at least two controls, otherwise the length is 0.</span></span>

## <a name="input"></a><span data-ttu-id="bd2b7-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="bd2b7-109">Input</span></span>

### <a name="auxregister--qubit"></a><span data-ttu-id="bd2b7-110">yedek kayıt: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bd2b7-110">auxRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="ctrlregister--qubit"></a><span data-ttu-id="bd2b7-111">ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bd2b7-111">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="bd2b7-112">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bd2b7-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="bd2b7-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd2b7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

