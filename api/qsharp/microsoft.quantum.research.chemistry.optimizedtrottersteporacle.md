---
uid: Microsoft.Quantum.Research.Chemistry.OptimizedTrotterStepOracle
title: Optimizedtroırsteporacle işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: OptimizedTrotterStepOracle
qsharp.summary: Returns optimized Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: f78d80f7ab71f4fc759d8045c9a134d7178aaa15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726378"
---
# <a name="optimizedtrottersteporacle-function"></a><span data-ttu-id="eeeef-102">Optimizedtroırsteporacle işlevi</span><span class="sxs-lookup"><span data-stu-id="eeeef-102">OptimizedTrotterStepOracle function</span></span>

<span data-ttu-id="eeeef-103">Ad alanı: [Microsoft. hisse. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="eeeef-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="eeeef-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eeeef-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eeeef-105">En iyileştirilmiş araba adımı işlemini ve çalıştırmak için gereken parametreleri döndürür.</span><span class="sxs-lookup"><span data-stu-id="eeeef-105">Returns optimized Trotter step operation and the parameters necessary to run it.</span></span>

```qsharp
function OptimizedTrotterStepOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, trotterStepSize : Double, trotterOrder : Int) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a><span data-ttu-id="eeeef-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="eeeef-106">Input</span></span>

### <a name="qsharpdata--jordanwignerencodingdata"></a><span data-ttu-id="eeeef-107">Qnetsveri: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="eeeef-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="eeeef-108">Hamiltonian biçim tarafından açıklanmıştır `JordanWignerEncodingData` .</span><span class="sxs-lookup"><span data-stu-id="eeeef-108">Hamiltonian described by `JordanWignerEncodingData` format.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="eeeef-109">Troesstepsize: [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eeeef-109">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eeeef-110">Rahatlık tümleştirici için adım boyutu.</span><span class="sxs-lookup"><span data-stu-id="eeeef-110">Step size of Trotter integrator.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="eeeef-111">Trokorder: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eeeef-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eeeef-112">Araba tümleştirici sırası.</span><span class="sxs-lookup"><span data-stu-id="eeeef-112">Order of Trotter integrator.</span></span>



## <a name="output--intdoublequbit--unit-adj--ctl"></a><span data-ttu-id="eeeef-113">Çıkış: ([Int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL))</span><span class="sxs-lookup"><span data-stu-id="eeeef-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl))</span></span>

<span data-ttu-id="eeeef-114">Bir demet:, `Int` ayrılan qubit sayısı,, `Double` `1.0/trotterStepSize` , ve işlem, sorun.</span><span class="sxs-lookup"><span data-stu-id="eeeef-114">A tuple where: `Int` is the number of qubits allocated, `Double` is `1.0/trotterStepSize`, and the operation is the Trotter step.</span></span>