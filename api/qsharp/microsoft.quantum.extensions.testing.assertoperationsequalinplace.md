---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualInPlace has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalinplace".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: 6d2ead95a60ed3cc8ee95fb7f91e1aa49d366a48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726774"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="b6033-102">AssertOperationsEqualInPlace işlemi</span><span class="sxs-lookup"><span data-stu-id="b6033-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="b6033-103">Ad alanı: [Microsoft. hisse. Extensions. test](xref:Microsoft.Quantum.Extensions.Testing)</span><span class="sxs-lookup"><span data-stu-id="b6033-103">Namespace: [Microsoft.Quantum.Extensions.Testing](xref:Microsoft.Quantum.Extensions.Testing)</span></span>

<span data-ttu-id="b6033-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6033-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="b6033-105">AssertOperationsEqualInPlace kullanım dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="b6033-105">AssertOperationsEqualInPlace has been deprecated.</span></span> <span data-ttu-id="b6033-106">Lütfen <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> bunun yerine kullanın.</span><span class="sxs-lookup"><span data-stu-id="b6033-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> instead.</span></span>
>
> <span data-ttu-id="b6033-107">Lütfen @"microsoft.quantum.diagnostics.assertoperationsequalinplace" kullanın.</span><span class="sxs-lookup"><span data-stu-id="b6033-107">Please use @"microsoft.quantum.diagnostics.assertoperationsequalinplace".</span></span>
> <span data-ttu-id="b6033-108">Bu işlem için bağımsız değişkenlerin sırasının değiştiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="b6033-108">Note that the order of the arguments to this operation has changed.</span></span>



```qsharp
operation AssertOperationsEqualInPlace (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a><span data-ttu-id="b6033-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="b6033-109">Input</span></span>

### <a name="actual--qubit--unit"></a><span data-ttu-id="b6033-110">gerçek: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b6033-110">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="expected--qubit--unit-adj"></a><span data-ttu-id="b6033-111">beklenen: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="b6033-111">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="nqubits--int"></a><span data-ttu-id="b6033-112">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b6033-112">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--unit"></a><span data-ttu-id="b6033-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b6033-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

