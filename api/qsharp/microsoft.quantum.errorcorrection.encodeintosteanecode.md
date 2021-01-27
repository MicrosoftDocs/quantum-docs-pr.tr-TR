---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: Encodeıntosteanecode işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 2f65423a17dafadd1f9f10a07335150dfc8bf886
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826199"
---
# <a name="encodeintosteanecode-operation"></a><span data-ttu-id="585fa-102">Encodeıntosteanecode işlemi</span><span class="sxs-lookup"><span data-stu-id="585fa-102">EncodeIntoSteaneCode operation</span></span>

<span data-ttu-id="585fa-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="585fa-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="585fa-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="585fa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="585fa-105">⟦ 7, 1, 3 ⟧ Steane hisse kodu altında kodlanmamış bir hisse CIL kaydını kodlanmış bir hisse kaydına eşleyen bir kodlama işlemi.</span><span class="sxs-lookup"><span data-stu-id="585fa-105">An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="585fa-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="585fa-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="585fa-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="585fa-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="585fa-108">Kodlanamayan bir hisse alma durumunu tutan bir qubit kaydı</span><span class="sxs-lookup"><span data-stu-id="585fa-108">A qubit register which holds the an unencoded quantum state</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="585fa-109">Kequbits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="585fa-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="585fa-110">Bir kodlama işleminin gerçekleştirilebilmesi için başlangıçta sıfır ve hisse sisteme eklenen bir qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="585fa-110">A qubit register which is initially zero and which gets added to the quantum system so that an encoding operation can be performed</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="585fa-111">Çıkış: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="585fa-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="585fa-112">Steane Kodlayıcısı uygulandıktan sonra durumu tutan bir hisse kaydı</span><span class="sxs-lookup"><span data-stu-id="585fa-112">A quantum register holding the state after the Steane encoder has been applied</span></span>

## <a name="see-also"></a><span data-ttu-id="585fa-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="585fa-113">See Also</span></span>

- [<span data-ttu-id="585fa-114">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="585fa-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="585fa-115">Microsoft. hisse. Errordüzeltmesini. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="585fa-115">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)