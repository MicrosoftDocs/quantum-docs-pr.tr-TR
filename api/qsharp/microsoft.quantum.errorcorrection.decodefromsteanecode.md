---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: Ayrılan Defromsteanecode işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 54e47b65ed7a89c8ff9026126a9542d3d7ba15cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827399"
---
# <a name="decodefromsteanecode-operation"></a><span data-ttu-id="339f3-102">Ayrılan Defromsteanecode işlemi</span><span class="sxs-lookup"><span data-stu-id="339f3-102">DecodeFromSteaneCode operation</span></span>

<span data-ttu-id="339f3-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="339f3-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="339f3-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="339f3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="339f3-105">⟦ 7, 1, 3 ⟧ Steane hisse kodu altında, kodlanmamış bir hisse CIL kaydını kodlanmış bir hisse kaydına eşleyen ters kodlama işlemi.</span><span class="sxs-lookup"><span data-stu-id="339f3-105">An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="339f3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="339f3-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="339f3-107">logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="339f3-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="339f3-108">Kodlanmış 5-qubit kodu mantıksal durumunu temsil eden bir qubits dizisi.</span><span class="sxs-lookup"><span data-stu-id="339f3-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="339f3-109">Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="339f3-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="339f3-110">İkinci parametrede yardımcı qubits ile birlikte ilk parametrede kodlanmamış durumu temsil eden bir qubit dizisi 1 uzunluğunda bir dizi.</span><span class="sxs-lookup"><span data-stu-id="339f3-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="339f3-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="339f3-111">Remarks</span></span>

<span data-ttu-id="339f3-112">Seçilen kod çözücüsü, ⟦ 7, 1, 3 ⟧ Steane kodunun CSS Code özelliğini kullanır, yani X hatalarını ve Z hatalarını ayrı olarak düzeltir.</span><span class="sxs-lookup"><span data-stu-id="339f3-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="339f3-113">Kodun bir özelliği, sırasıyla x, sırasıyla z özelliğinin, bir tamsayı kabul edildiğinde x, z sendromu 'nin 3 bitlik kodlamasıdır.</span><span class="sxs-lookup"><span data-stu-id="339f3-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="339f3-114">Başvurular</span><span class="sxs-lookup"><span data-stu-id="339f3-114">References</span></span>

- <span data-ttu-id="339f3-115">D.</span><span class="sxs-lookup"><span data-stu-id="339f3-115">D.</span></span> <span data-ttu-id="339f3-116">Gottesman, "sabitleyici kodlar ve hisse hata düzeltmesi," Ph.D. sıra, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="339f3-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="339f3-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="339f3-117">See Also</span></span>

- [<span data-ttu-id="339f3-118">Microsoft. hisse. Errordüzeltmesini. SteaneCodeEncoder</span><span class="sxs-lookup"><span data-stu-id="339f3-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [<span data-ttu-id="339f3-119">Microsoft. hisse. Errordüzeltmesini. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="339f3-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [<span data-ttu-id="339f3-120">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="339f3-120">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)