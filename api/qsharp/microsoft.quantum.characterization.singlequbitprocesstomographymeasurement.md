---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: Singlequbitprocesstomographyıölçüm işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 34e5143d5be316ee42a63124d35475949db0a692
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728166"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a><span data-ttu-id="683da-102">Singlequbitprocesstomographyıölçüm işlemi</span><span class="sxs-lookup"><span data-stu-id="683da-102">SingleQubitProcessTomographyMeasurement operation</span></span>

<span data-ttu-id="683da-103">Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="683da-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="683da-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="683da-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="683da-105">, Belirli bir ilgi kanalı verildiğinde Pauli temelinde tek qubit işlem işlemleri gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="683da-105">Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.</span></span>

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a><span data-ttu-id="683da-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="683da-106">Input</span></span>

### <a name="preparation--pauli"></a><span data-ttu-id="683da-107">Hazırlık: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="683da-107">preparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="683da-108">Bir qubit 'in hazırlanmakta olduğu Pauli temel öğesi $P $.</span><span class="sxs-lookup"><span data-stu-id="683da-108">The Pauli basis element $P$ in which a qubit is to be prepared.</span></span>


### <a name="measurement--pauli"></a><span data-ttu-id="683da-109">ölçüm: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="683da-109">measurement : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="683da-110">Bir qubit 'in ölçülecek olan Pauli temel öğesi $Q.</span><span class="sxs-lookup"><span data-stu-id="683da-110">The Pauli basis element $Q$ in which a qubit is to be measured.</span></span>


### <a name="channel--qubit--unit"></a><span data-ttu-id="683da-111">Kanal: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="683da-111">channel : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="683da-112">Tek bir qubit kanalı $ \Lambda $, davranışları işlem turununile tahmin ediliyor.</span><span class="sxs-lookup"><span data-stu-id="683da-112">A single qubit channel $\Lambda$ whose behavior is being estimated with process tomography.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="683da-113">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="683da-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="683da-114">`Zero`Olasılığa sahip sonuç $ $ \begin{hizalaması} \Pr (\Texttt{dd} | \Lambda; P, Q) = \operatorname{Tr}\left (\frac{\cıvadone + Q} {2} \Lambalo\left [\frac{\cıvadone + P} {2} \ sağ] \ sağ).</span><span class="sxs-lookup"><span data-stu-id="683da-114">The Result `Zero` with probability $$ \begin{align} \Pr(\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left( \frac{\boldone + Q}{2} \Lambda\left[ \frac{\boldone + P}{2} \right] \right).</span></span>
<span data-ttu-id="683da-115">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="683da-115">\end{align} $$</span></span>

## <a name="remarks"></a><span data-ttu-id="683da-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="683da-116">Remarks</span></span>

<span data-ttu-id="683da-117">Bu işlem tarafından döndürülen sonuçların üzerine dağıtım, iki-qubit durumu tomografi özel bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="683da-117">The distribution over results returned by this operation is a special case of two-qubit state tomography.</span></span> <span data-ttu-id="683da-118">$ \ Lambda $ için Choi – Jamiłkowski durumu $ \rho = J (\Lambda)/$2 olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="683da-118">Let $\rho = J(\Lambda) / 2$ be the Choi–Jamiłkowski state for $\Lambda$.</span></span> <span data-ttu-id="683da-119">Daha sonra, yukarıdaki dağıtım $ $ \begin{hizalaması} \Pr (\Texttt{dd} | \rho; ile aynıdır. M) = \operatorname{Tr} (M \rho), \end{hizalaması} $ $ burada $M = 2 (\cıvadone + P) ^ \mathrm{T}/2 \cdot (\cıvadone + Q)/$2, $P $ ve $Q $ öğesine karşılık gelen etkili ölçümdür.</span><span class="sxs-lookup"><span data-stu-id="683da-119">Then, the distribution above is identical to $$ \begin{align} \Pr(\texttt{Zero} | \rho; M) = \operatorname{Tr}(M \rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ is the effective measurement corresponding to $P$ and $Q$.</span></span>