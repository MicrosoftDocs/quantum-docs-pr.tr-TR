---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: Fivequbitcodeencoderımpl işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: f70d2d1352c7b2eebee7a863eba97d78d7351dab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200858"
---
# <a name="fivequbitcodeencoderimpl-operation"></a><span data-ttu-id="21422-102">Fivequbitcodeencoderımpl işlemi</span><span class="sxs-lookup"><span data-stu-id="21422-102">FiveQubitCodeEncoderImpl operation</span></span>

<span data-ttu-id="21422-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="21422-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="21422-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="21422-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="21422-105">Hem 5 qubit Kodlayıcı hem de kod çözücü uygulamak için kullanılan özel işlem.</span><span class="sxs-lookup"><span data-stu-id="21422-105">Private operation used to implement both the 5 qubit encoder and decoder.</span></span>

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="21422-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="21422-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="21422-107">veri: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="21422-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="21422-108">Giriş qubit olan 1 qubit tutan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="21422-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="21422-109">karalama: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="21422-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="21422-110">artıklık ekleyen 4 qubit tutan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="21422-110">an array holding 4 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="21422-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="21422-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="21422-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="21422-112">Remarks</span></span>

<span data-ttu-id="21422-113">Seçilen belirli bir kodlayıcı, V. Kliuchnikov ve D. Maslov, "Clifford devreleri," fiziksel. Rev. fiziksel. Rev. A 88, 052307 (2013) ' den alınmıştır. https://arxiv.org/abs/1305.0810, Şekil 4b) ve toplam 11 kapı gerektirir.</span><span class="sxs-lookup"><span data-stu-id="21422-113">The particular encoder chosen was taken from the paper V. Kliuchnikov and D. Maslov, "Optimization of Clifford Circuits," Phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) and requires a total of 11 gates.</span></span>