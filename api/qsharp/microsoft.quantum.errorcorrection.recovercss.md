---
uid: Microsoft.Quantum.ErrorCorrection.RecoverCSS
title: RecoverCSS işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoverCSS
qsharp.summary: Performs a single round of error correction by a quantum code described by a `CSS` type.
ms.openlocfilehash: 48d3cd3d5f6aea265fac2f50b913ab855a31accf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727001"
---
# <a name="recovercss-operation"></a><span data-ttu-id="381e5-102">RecoverCSS işlemi</span><span class="sxs-lookup"><span data-stu-id="381e5-102">RecoverCSS operation</span></span>

<span data-ttu-id="381e5-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="381e5-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="381e5-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="381e5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="381e5-105">Bir tür tarafından tanımlanan bir hisse kodu tarafından hata düzeltmesinin tek bir yuvarlamesi gerçekleştirir `CSS` .</span><span class="sxs-lookup"><span data-stu-id="381e5-105">Performs a single round of error correction by a quantum code described by a `CSS` type.</span></span>

```qsharp
operation RecoverCSS (code : Microsoft.Quantum.ErrorCorrection.CSS, fnX : Microsoft.Quantum.ErrorCorrection.RecoveryFn, fnZ : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="381e5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="381e5-106">Input</span></span>

### <a name="code--css"></a><span data-ttu-id="381e5-107">kod: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="381e5-107">code : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="381e5-108">Hisse ve bir tür olarak paketlenmiş kod düzeltme kodu, `CSS` hisse verileri kodlamasını ve kodunu çözmeyi ve hata eşitleme 'nin nasıl ölçüldüğünü açıklar.</span><span class="sxs-lookup"><span data-stu-id="381e5-108">A quantum CSS error-correcting code packaged as a `CSS` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fnx--recoveryfn"></a><span data-ttu-id="381e5-109">fnX: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="381e5-109">fnX : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="381e5-110">`RecoveryFn`Her bir $X $ hata syndrobeni, `Pauli[]` algılanan hatayı düzeltecek işlemlere eşler.</span><span class="sxs-lookup"><span data-stu-id="381e5-110">A `RecoveryFn` that maps each $X$ error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="fnz--recoveryfn"></a><span data-ttu-id="381e5-111">fnZ: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="381e5-111">fnZ : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="381e5-112">`RecoveryFn`Her bir $Z $ hata syndrobeni, `Pauli[]` algılanan hatayı düzeltecek işlemlere eşler.</span><span class="sxs-lookup"><span data-stu-id="381e5-112">A `RecoveryFn` that maps each $Z$ error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="381e5-113">logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="381e5-113">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="381e5-114">Sabitleyici kodun tanımlandığı bir qubits dizisi.</span><span class="sxs-lookup"><span data-stu-id="381e5-114">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="381e5-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="381e5-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="381e5-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="381e5-116">See Also</span></span>

- [<span data-ttu-id="381e5-117">Microsoft. hisse. Errordüzeltmesini. CSS</span><span class="sxs-lookup"><span data-stu-id="381e5-117">Microsoft.Quantum.ErrorCorrection.CSS</span></span>](xref:Microsoft.Quantum.ErrorCorrection.CSS)
- [<span data-ttu-id="381e5-118">Microsoft. hisse. Errordüzeltmesini. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="381e5-118">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="381e5-119">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="381e5-119">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)