---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: Fivequbitcodeencoderımpl işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 29b0f47ddffeae3ed4dfda4084304427418e02fd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727056"
---
# <a name="fivequbitcodeencoderimpl-operation"></a><span data-ttu-id="c37d9-102">Fivequbitcodeencoderımpl işlemi</span><span class="sxs-lookup"><span data-stu-id="c37d9-102">FiveQubitCodeEncoderImpl operation</span></span>

<span data-ttu-id="c37d9-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c37d9-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c37d9-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c37d9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c37d9-105">Hem 5 qubit Kodlayıcı hem de kod çözücü uygulamak için kullanılan özel işlem.</span><span class="sxs-lookup"><span data-stu-id="c37d9-105">Private operation used to implement both the 5 qubit encoder and decoder.</span></span>

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c37d9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c37d9-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="c37d9-107">veri: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c37d9-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c37d9-108">Giriş qubit olan 1 qubit tutan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="c37d9-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="c37d9-109">karalama: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c37d9-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c37d9-110">artıklık ekleyen 4 qubit tutan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="c37d9-110">an array holding 4 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c37d9-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c37d9-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c37d9-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c37d9-112">Remarks</span></span>

<span data-ttu-id="c37d9-113">Seçilen belirli bir kodlayıcı, V. Kliuchnikov ve D. Maslov, "Clifford devreleri," fiziksel. Rev. fiziksel. Rev. A 88, 052307 (2013) ' den alınmıştır. https://arxiv.org/abs/1305.0810, Şekil 4b) ve toplam 11 kapı gerektirir.</span><span class="sxs-lookup"><span data-stu-id="c37d9-113">The particular encoder chosen was taken from the paper V. Kliuchnikov and D. Maslov, "Optimization of Clifford Circuits," Phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) and requires a total of 11 gates.</span></span>