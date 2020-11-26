---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: Nicetumromqubitcount işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 0ec1e042b9f675505f73bfcdcc6706d0bc0367df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210412"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="e11b3-102">Nicetumromqubitcount işlevi</span><span class="sxs-lookup"><span data-stu-id="e11b3-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="e11b3-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e11b3-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e11b3-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e11b3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="e11b3-105">Miktar Tumromqubitcount kullanım dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="e11b3-105">QuantumROMQubitCount has been deprecated.</span></span> <span data-ttu-id="e11b3-106">Lütfen <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> bunun yerine kullanın.</span><span class="sxs-lookup"><span data-stu-id="e11b3-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.</span></span>

<span data-ttu-id="e11b3-107">Tarafından döndürülen işleme ayrılması gereken qubits sayısının toplam sayısını döndürür `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="e11b3-107">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="e11b3-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="e11b3-108">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="e11b3-109">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e11b3-109">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e11b3-110">Hedef hata $ \ Epsilon $.</span><span class="sxs-lookup"><span data-stu-id="e11b3-110">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="e11b3-111">nCoeffs: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e11b3-111">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e11b3-112">İçinde belirtilen katsayının sayısı `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="e11b3-112">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="e11b3-113">Çıkış: ([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)))</span><span class="sxs-lookup"><span data-stu-id="e11b3-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="e11b3-114">İlk parametre</span><span class="sxs-lookup"><span data-stu-id="e11b3-114">First parameter</span></span>

<span data-ttu-id="e11b3-115">`(x,(y,z))` `x = y + z` Ayrılan toplam qubit sayısı, `y` yazmaç için qubit sayısı `LittleEndian` ve `z` çöp qubit sayısı olan bir kayıt düzeni.</span><span class="sxs-lookup"><span data-stu-id="e11b3-115">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>