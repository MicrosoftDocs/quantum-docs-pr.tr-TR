---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: Ayrılan Defromsteanecode işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: e6831a8630c0a80c2abe7c4a720263f0de03edc4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727092"
---
# <a name="decodefromsteanecode-operation"></a><span data-ttu-id="b1b9f-102">Ayrılan Defromsteanecode işlemi</span><span class="sxs-lookup"><span data-stu-id="b1b9f-102">DecodeFromSteaneCode operation</span></span>

<span data-ttu-id="b1b9f-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="b1b9f-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="b1b9f-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b1b9f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b1b9f-105">⟦ 7, 1, 3 ⟧ Steane hisse kodu altında, kodlanmamış bir hisse CIL kaydını kodlanmış bir hisse kaydına eşleyen ters kodlama işlemi.</span><span class="sxs-lookup"><span data-stu-id="b1b9f-105">An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="b1b9f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="b1b9f-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="b1b9f-107">logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="b1b9f-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="b1b9f-108">Kodlanmış 5-qubit kodu mantıksal durumunu temsil eden bir qubits dizisi.</span><span class="sxs-lookup"><span data-stu-id="b1b9f-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="b1b9f-109">Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="b1b9f-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="b1b9f-110">İkinci parametrede yardımcı qubits ile birlikte ilk parametrede kodlanmamış durumu temsil eden bir qubit dizisi 1 uzunluğunda bir dizi.</span><span class="sxs-lookup"><span data-stu-id="b1b9f-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1b9f-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b1b9f-111">Remarks</span></span>

<span data-ttu-id="b1b9f-112">Seçilen kod çözücüsü, ⟦ 7, 1, 3 ⟧ Steane kodunun CSS Code özelliğini kullanır, yani X hatalarını ve Z hatalarını ayrı olarak düzeltir.</span><span class="sxs-lookup"><span data-stu-id="b1b9f-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="b1b9f-113">Kodun bir özelliği, sırasıyla x, sırasıyla z özelliğinin, bir tamsayı kabul edildiğinde x, z sendromu 'nin 3 bitlik kodlamasıdır.</span><span class="sxs-lookup"><span data-stu-id="b1b9f-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="b1b9f-114">Referanslar</span><span class="sxs-lookup"><span data-stu-id="b1b9f-114">References</span></span>

- <span data-ttu-id="b1b9f-115">D.</span><span class="sxs-lookup"><span data-stu-id="b1b9f-115">D.</span></span> <span data-ttu-id="b1b9f-116">Gottesman, "sabitleyici kodlar ve hisse hata düzeltmesi," Ph.D. sıra, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="b1b9f-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="b1b9f-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b1b9f-117">See Also</span></span>

- [<span data-ttu-id="b1b9f-118">Microsoft. hisse. Errordüzeltmesini. SteaneCodeEncoder</span><span class="sxs-lookup"><span data-stu-id="b1b9f-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [<span data-ttu-id="b1b9f-119">Microsoft. hisse. Errordüzeltmesini. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="b1b9f-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [<span data-ttu-id="b1b9f-120">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="b1b9f-120">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)