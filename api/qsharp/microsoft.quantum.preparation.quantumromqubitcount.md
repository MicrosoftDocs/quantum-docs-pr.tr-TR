---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: Nicetumromqubitcount işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: d6eac64eb62ec7a88d3231249b0bb1e05818f6e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856806"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="477ad-102">Nicetumromqubitcount işlevi</span><span class="sxs-lookup"><span data-stu-id="477ad-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="477ad-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="477ad-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="477ad-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="477ad-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="477ad-105">Miktar Tumromqubitcount kullanım dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="477ad-105">QuantumROMQubitCount has been deprecated.</span></span> <span data-ttu-id="477ad-106">Lütfen <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> bunun yerine kullanın.</span><span class="sxs-lookup"><span data-stu-id="477ad-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.</span></span>

<span data-ttu-id="477ad-107">Tarafından döndürülen işleme ayrılması gereken qubits sayısının toplam sayısını döndürür `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="477ad-107">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="477ad-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="477ad-108">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="477ad-109">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="477ad-109">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="477ad-110">Hedef hata $ \ Epsilon $.</span><span class="sxs-lookup"><span data-stu-id="477ad-110">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="477ad-111">nCoeffs: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="477ad-111">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="477ad-112">İçinde belirtilen katsayının sayısı `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="477ad-112">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="477ad-113">Çıkış: ([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)))</span><span class="sxs-lookup"><span data-stu-id="477ad-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="477ad-114">İlk parametre</span><span class="sxs-lookup"><span data-stu-id="477ad-114">First parameter</span></span>

<span data-ttu-id="477ad-115">`(x,(y,z))` `x = y + z` Ayrılan toplam qubit sayısı, `y` yazmaç için qubit sayısı `LittleEndian` ve `z` çöp qubit sayısı olan bir kayıt düzeni.</span><span class="sxs-lookup"><span data-stu-id="477ad-115">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>