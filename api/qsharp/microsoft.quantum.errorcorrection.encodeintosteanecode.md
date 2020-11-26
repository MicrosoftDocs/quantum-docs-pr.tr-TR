---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: Encodeıntosteanecode işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: e74c7fdc5acbb1a8c417bad3eb3630314e3f71bc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201028"
---
# <a name="encodeintosteanecode-operation"></a><span data-ttu-id="360af-102">Encodeıntosteanecode işlemi</span><span class="sxs-lookup"><span data-stu-id="360af-102">EncodeIntoSteaneCode operation</span></span>

<span data-ttu-id="360af-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="360af-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="360af-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="360af-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="360af-105">⟦ 7, 1, 3 ⟧ Steane hisse kodu altında kodlanmamış bir hisse CIL kaydını kodlanmış bir hisse kaydına eşleyen bir kodlama işlemi.</span><span class="sxs-lookup"><span data-stu-id="360af-105">An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="360af-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="360af-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="360af-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="360af-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="360af-108">Kodlanamayan bir hisse alma durumunu tutan bir qubit kaydı</span><span class="sxs-lookup"><span data-stu-id="360af-108">A qubit register which holds the an unencoded quantum state</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="360af-109">Kequbits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="360af-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="360af-110">Bir kodlama işleminin gerçekleştirilebilmesi için başlangıçta sıfır ve hisse sisteme eklenen bir qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="360af-110">A qubit register which is initially zero and which gets added to the quantum system so that an encoding operation can be performed</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="360af-111">Çıkış: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="360af-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="360af-112">Steane Kodlayıcısı uygulandıktan sonra durumu tutan bir hisse kaydı</span><span class="sxs-lookup"><span data-stu-id="360af-112">A quantum register holding the state after the Steane encoder has been applied</span></span>

## <a name="see-also"></a><span data-ttu-id="360af-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="360af-113">See Also</span></span>

- [<span data-ttu-id="360af-114">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="360af-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="360af-115">Microsoft. hisse. Errordüzeltmesini. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="360af-115">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)