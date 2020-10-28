---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: Steanecodeencoderımpl işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: b843422a6007d01de9b57ec659c229b8ab0ad2e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726995"
---
# <a name="steanecodeencoderimpl-operation"></a><span data-ttu-id="58f26-102">Steanecodeencoderımpl işlemi</span><span class="sxs-lookup"><span data-stu-id="58f26-102">SteaneCodeEncoderImpl operation</span></span>

<span data-ttu-id="58f26-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="58f26-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="58f26-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="58f26-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="58f26-105">Hem Steane kod Kodlayıcısı hem de kod çözücü uygulamak için kullanılan özel işlem.</span><span class="sxs-lookup"><span data-stu-id="58f26-105">Private operation used to implement both the Steane code encoder and decoder.</span></span>

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="58f26-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="58f26-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="58f26-107">veri: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="58f26-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="58f26-108">Giriş qubit olan 1 qubit tutan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="58f26-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="58f26-109">karalama: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="58f26-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="58f26-110">artıklık ekleyen 6 qubit tutan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="58f26-110">an array holding 6 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="58f26-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="58f26-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

