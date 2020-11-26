---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: Kurtarma işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: bdf09decc3705d3285f4eb605c176d7764a994d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200586"
---
# <a name="recover-operation"></a><span data-ttu-id="14630-102">Kurtarma işlemi</span><span class="sxs-lookup"><span data-stu-id="14630-102">Recover operation</span></span>

<span data-ttu-id="14630-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="14630-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="14630-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="14630-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="14630-105">Bir tür tarafından tanımlanan bir hisse kodu tarafından hata düzeltmesinin tek bir yuvarlamesi gerçekleştirir `QECC` .</span><span class="sxs-lookup"><span data-stu-id="14630-105">Performs a single round of error correction by a quantum code described by a `QECC` type.</span></span>

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="14630-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="14630-106">Input</span></span>

### <a name="code--qecc"></a><span data-ttu-id="14630-107">kod: [Qecc](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="14630-107">code : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="14630-108">Hisse hatası-bir tür olarak paketlenmiş kod düzeltme, `QECC` hisse verileri kodlamasını ve kodunu çözmeyi ve hata eşitleme 'nin nasıl ölçüldüğünü açıklar.</span><span class="sxs-lookup"><span data-stu-id="14630-108">A quantum error-correcting code packaged as a `QECC` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fn--recoveryfn"></a><span data-ttu-id="14630-109">FN: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="14630-109">fn : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="14630-110">`RecoveryFn`Bu her bir hatayı, algılanan hatayı düzeltmek için her bir hata sendromu eşleyen `Pauli[]` işlemlere eşler.</span><span class="sxs-lookup"><span data-stu-id="14630-110">A `RecoveryFn` that maps each error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="14630-111">logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="14630-111">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="14630-112">Sabitleyici kodun tanımlandığı bir qubits dizisi.</span><span class="sxs-lookup"><span data-stu-id="14630-112">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="14630-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14630-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="14630-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="14630-114">See Also</span></span>

- [<span data-ttu-id="14630-115">Microsoft. hisse. Errordüzeltmesini. QECC</span><span class="sxs-lookup"><span data-stu-id="14630-115">Microsoft.Quantum.ErrorCorrection.QECC</span></span>](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [<span data-ttu-id="14630-116">Microsoft. hisse. Errordüzeltmesini. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="14630-116">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="14630-117">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="14630-117">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)