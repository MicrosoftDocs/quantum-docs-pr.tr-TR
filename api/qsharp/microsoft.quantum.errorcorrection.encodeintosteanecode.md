---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: Encodeıntosteanecode işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 39b8ab549413d9d5281f6b84a6e970c45242fca8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727080"
---
# <a name="encodeintosteanecode-operation"></a><span data-ttu-id="d74d5-102">Encodeıntosteanecode işlemi</span><span class="sxs-lookup"><span data-stu-id="d74d5-102">EncodeIntoSteaneCode operation</span></span>

<span data-ttu-id="d74d5-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="d74d5-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="d74d5-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d74d5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d74d5-105">⟦ 7, 1, 3 ⟧ Steane hisse kodu altında kodlanmamış bir hisse CIL kaydını kodlanmış bir hisse kaydına eşleyen bir kodlama işlemi.</span><span class="sxs-lookup"><span data-stu-id="d74d5-105">An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="d74d5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d74d5-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="d74d5-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d74d5-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d74d5-108">Kodlanamayan bir hisse alma durumunu tutan bir qubit kaydı</span><span class="sxs-lookup"><span data-stu-id="d74d5-108">A qubit register which holds the an unencoded quantum state</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="d74d5-109">Kequbits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d74d5-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d74d5-110">Bir kodlama işleminin gerçekleştirilebilmesi için başlangıçta sıfır ve hisse sisteme eklenen bir qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="d74d5-110">A qubit register which is initially zero and which gets added to the quantum system so that an encoding operation can be performed</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="d74d5-111">Çıkış: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="d74d5-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="d74d5-112">Steane Kodlayıcısı uygulandıktan sonra durumu tutan bir hisse kaydı</span><span class="sxs-lookup"><span data-stu-id="d74d5-112">A quantum register holding the state after the Steane encoder has been applied</span></span>

## <a name="see-also"></a><span data-ttu-id="d74d5-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d74d5-113">See Also</span></span>

- [<span data-ttu-id="d74d5-114">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="d74d5-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="d74d5-115">Microsoft. hisse. Errordüzeltmesini. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="d74d5-115">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)