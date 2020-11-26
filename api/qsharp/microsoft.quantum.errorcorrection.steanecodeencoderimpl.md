---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: Steanecodeencoderımpl işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: 3a9a1b11ed9255f18135e3717de7e9e1ec891298
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200437"
---
# <a name="steanecodeencoderimpl-operation"></a><span data-ttu-id="19256-102">Steanecodeencoderımpl işlemi</span><span class="sxs-lookup"><span data-stu-id="19256-102">SteaneCodeEncoderImpl operation</span></span>

<span data-ttu-id="19256-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="19256-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="19256-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="19256-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="19256-105">Hem Steane kod Kodlayıcısı hem de kod çözücü uygulamak için kullanılan özel işlem.</span><span class="sxs-lookup"><span data-stu-id="19256-105">Private operation used to implement both the Steane code encoder and decoder.</span></span>

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="19256-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="19256-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="19256-107">veri: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="19256-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="19256-108">Giriş qubit olan 1 qubit tutan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="19256-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="19256-109">karalama: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="19256-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="19256-110">artıklık ekleyen 6 qubit tutan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="19256-110">an array holding 6 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="19256-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="19256-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

