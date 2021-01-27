---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: b4f6c3ca28e2976b6a0d58f4ef25ea943de9811e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854885"
---
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="f841f-102">StateGenerator Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="f841f-102">StateGenerator user defined type</span></span>

<span data-ttu-id="f841f-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f841f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f841f-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f841f-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="f841f-105">Belirli bir girişi sıralı sınıflandırıcıya hazırlayan bir işlem açıklar.</span><span class="sxs-lookup"><span data-stu-id="f841f-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="f841f-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="f841f-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="f841f-107">NQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f841f-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f841f-108">Kodlanan girişin tanımlandığı qubit sayısı.</span><span class="sxs-lookup"><span data-stu-id="f841f-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="f841f-109">Prepare: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL</span><span class="sxs-lookup"><span data-stu-id="f841f-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f841f-110">Bir qubits 'in küçük endian kaydındaki kodlanmış girişi hazırlayan bir işlem `NQubits` .</span><span class="sxs-lookup"><span data-stu-id="f841f-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>