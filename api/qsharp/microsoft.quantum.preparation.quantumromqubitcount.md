---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: Nicetumromqubitcount işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 988d5efa3e27cf5e9a276ab3ab443c10f88fe1ad
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732607"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="79970-102">Nicetumromqubitcount işlevi</span><span class="sxs-lookup"><span data-stu-id="79970-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="79970-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="79970-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="79970-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="79970-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="79970-105">Tarafından döndürülen işleme ayrılması gereken qubits sayısının toplam sayısını döndürür `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="79970-105">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="79970-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="79970-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="79970-107">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="79970-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="79970-108">Hedef hata $ \ Epsilon $.</span><span class="sxs-lookup"><span data-stu-id="79970-108">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="79970-109">nCoeffs: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="79970-109">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="79970-110">İçinde belirtilen katsayının sayısı `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="79970-110">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="79970-111">Çıkış: ([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)))</span><span class="sxs-lookup"><span data-stu-id="79970-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="79970-112">İlk parametre</span><span class="sxs-lookup"><span data-stu-id="79970-112">First parameter</span></span>

<span data-ttu-id="79970-113">`(x,(y,z))` `x = y + z` Ayrılan toplam qubit sayısı, `y` yazmaç için qubit sayısı `LittleEndian` ve `z` çöp qubit sayısı olan bir kayıt düzeni.</span><span class="sxs-lookup"><span data-stu-id="79970-113">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>