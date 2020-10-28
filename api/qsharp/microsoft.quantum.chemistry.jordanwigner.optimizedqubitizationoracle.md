---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedQubitizationOracle
title: Optimizedqubitişzationoracle işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedQubitizationOracle
qsharp.summary: Returns T-count optimized Qubitization operation and the parameters necessary to run it.
ms.openlocfilehash: c67dc5890fe1444c1689eb803ed3d24b2dbe5ce2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727722"
---
# <a name="optimizedqubitizationoracle-function"></a><span data-ttu-id="acdfa-102">Optimizedqubitişzationoracle işlevi</span><span class="sxs-lookup"><span data-stu-id="acdfa-102">OptimizedQubitizationOracle function</span></span>

<span data-ttu-id="acdfa-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="acdfa-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="acdfa-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="acdfa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="acdfa-105">T-say iyileştirilmiş Qubitişleştirme işlemini ve çalıştırmak için gereken parametreleri döndürür.</span><span class="sxs-lookup"><span data-stu-id="acdfa-105">Returns T-count optimized Qubitization operation and the parameters necessary to run it.</span></span>

```qsharp
function OptimizedQubitizationOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, targetError : Double) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a><span data-ttu-id="acdfa-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="acdfa-106">Input</span></span>

### <a name="qsharpdata--jordanwignerencodingdata"></a><span data-ttu-id="acdfa-107">Qnetsveri: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="acdfa-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="acdfa-108">Hamiltonian biçim tarafından açıklanmıştır `JordanWignerEncodingData` .</span><span class="sxs-lookup"><span data-stu-id="acdfa-108">Hamiltonian described by `JordanWignerEncodingData` format.</span></span>


### <a name="targeterror--double"></a><span data-ttu-id="acdfa-109">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="acdfa-109">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="acdfa-110">Yardımcı durum hazırlama adımının hatası.</span><span class="sxs-lookup"><span data-stu-id="acdfa-110">Error of auxillary state preparation step.</span></span>



## <a name="output--intdoublequbit--unit-adj--ctl"></a><span data-ttu-id="acdfa-111">Çıkış: ([Int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL))</span><span class="sxs-lookup"><span data-stu-id="acdfa-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl))</span></span>

<span data-ttu-id="acdfa-112">Bir kayıt düzeni: `Int` ayrılan qubit sayısı, `Double` Hamiltonian katsayısının tek norm ve Işlem, Qubitişleştirme tarafından oluşturulan hisse alma işlemidir.</span><span class="sxs-lookup"><span data-stu-id="acdfa-112">A tuple where: `Int` is the number of qubits allocated, `Double` is the one-norm of Hamiltonian coefficients, and the operation is the Quantum walk created by Qubitization.</span></span>