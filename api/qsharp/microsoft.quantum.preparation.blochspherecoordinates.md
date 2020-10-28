---
uid: Microsoft.Quantum.Preparation.BlochSphereCoordinates
title: Blochspburkoordinatları işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: BlochSphereCoordinates
qsharp.summary: >-
  Computes the Bloch sphere coordinates for a single-qubit state.

  Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.
ms.openlocfilehash: 6614b78c8e64c205cc94052cc64dd957814ab3d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733263"
---
# <a name="blochspherecoordinates-function"></a><span data-ttu-id="2c90a-102">Blochspburkoordinatları işlevi</span><span class="sxs-lookup"><span data-stu-id="2c90a-102">BlochSphereCoordinates function</span></span>

<span data-ttu-id="2c90a-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="2c90a-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="2c90a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2c90a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2c90a-105">Tek qubit durumu için Bloch Sphere koordinatlarını hesaplar.</span><span class="sxs-lookup"><span data-stu-id="2c90a-105">Computes the Bloch sphere coordinates for a single-qubit state.</span></span>

<span data-ttu-id="2c90a-106">Bu iki karmaşık sayı $a, qubit durumunu temsil eden 0, a1 $, $a 0 \ ayraç {0} + a1 \ {1} Tus= r e ^ {it} (e ^ {-ı \phi/2}\cos{(\ teta/2)} {0} \tus+ e ^ {ı \fi/2}\sin{(\ teta/2)} \ket {1} ) $.</span><span class="sxs-lookup"><span data-stu-id="2c90a-106">Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.</span></span>

```qsharp
function BlochSphereCoordinates (a0 : Microsoft.Quantum.Math.ComplexPolar, a1 : Microsoft.Quantum.Math.ComplexPolar) : (Microsoft.Quantum.Math.ComplexPolar, Double, Double)
```


## <a name="input"></a><span data-ttu-id="2c90a-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="2c90a-107">Input</span></span>

### <a name="a0--complexpolar"></a><span data-ttu-id="2c90a-108">a0: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="2c90a-108">a0 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="2c90a-109">Karmaşık katsayı devleti $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="2c90a-109">Complex coefficient of state $\ket{0}$.</span></span>


### <a name="a1--complexpolar"></a><span data-ttu-id="2c90a-110">a1: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="2c90a-110">a1 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="2c90a-111">Karmaşık katsayı devleti $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="2c90a-111">Complex coefficient of state $\ket{1}$.</span></span>



## <a name="output--complexpolardoubledouble"></a><span data-ttu-id="2c90a-112">Çıkış: ([Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar),[Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="2c90a-112">Output : ([ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar),[Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="2c90a-113">İçeren bir tanımlama grubu `(ComplexPolar(r, t), phi, theta)` .</span><span class="sxs-lookup"><span data-stu-id="2c90a-113">A tuple containing `(ComplexPolar(r, t), phi, theta)`.</span></span>