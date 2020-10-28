---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: Kurtarma işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: a659399f51794a4edc1d2ff43da84e46797103fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727002"
---
# <a name="recover-operation"></a><span data-ttu-id="ce315-102">Kurtarma işlemi</span><span class="sxs-lookup"><span data-stu-id="ce315-102">Recover operation</span></span>

<span data-ttu-id="ce315-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="ce315-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="ce315-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ce315-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ce315-105">Bir tür tarafından tanımlanan bir hisse kodu tarafından hata düzeltmesinin tek bir yuvarlamesi gerçekleştirir `QECC` .</span><span class="sxs-lookup"><span data-stu-id="ce315-105">Performs a single round of error correction by a quantum code described by a `QECC` type.</span></span>

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="ce315-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ce315-106">Input</span></span>

### <a name="code--qecc"></a><span data-ttu-id="ce315-107">kod: [Qecc](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="ce315-107">code : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="ce315-108">Hisse hatası-bir tür olarak paketlenmiş kod düzeltme, `QECC` hisse verileri kodlamasını ve kodunu çözmeyi ve hata eşitleme 'nin nasıl ölçüldüğünü açıklar.</span><span class="sxs-lookup"><span data-stu-id="ce315-108">A quantum error-correcting code packaged as a `QECC` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fn--recoveryfn"></a><span data-ttu-id="ce315-109">FN: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="ce315-109">fn : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="ce315-110">`RecoveryFn`Bu her bir hatayı, algılanan hatayı düzeltmek için her bir hata sendromu eşleyen `Pauli[]` işlemlere eşler.</span><span class="sxs-lookup"><span data-stu-id="ce315-110">A `RecoveryFn` that maps each error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="ce315-111">logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="ce315-111">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="ce315-112">Sabitleyici kodun tanımlandığı bir qubits dizisi.</span><span class="sxs-lookup"><span data-stu-id="ce315-112">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ce315-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ce315-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ce315-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ce315-114">See Also</span></span>

- [<span data-ttu-id="ce315-115">Microsoft. hisse. Errordüzeltmesini. QECC</span><span class="sxs-lookup"><span data-stu-id="ce315-115">Microsoft.Quantum.ErrorCorrection.QECC</span></span>](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [<span data-ttu-id="ce315-116">Microsoft. hisse. Errordüzeltmesini. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="ce315-116">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="ce315-117">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="ce315-117">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)