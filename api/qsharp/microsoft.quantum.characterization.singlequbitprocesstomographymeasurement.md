---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: Singlequbitprocesstomographyıölçüm işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 883b98ad4f2d0ac4a02e55e444c04e8e7cf37af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839648"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a><span data-ttu-id="cc311-102">Singlequbitprocesstomographyıölçüm işlemi</span><span class="sxs-lookup"><span data-stu-id="cc311-102">SingleQubitProcessTomographyMeasurement operation</span></span>

<span data-ttu-id="cc311-103">Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="cc311-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="cc311-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cc311-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cc311-105">, Belirli bir ilgi kanalı verildiğinde Pauli temelinde tek qubit işlem işlemleri gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="cc311-105">Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.</span></span>

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a><span data-ttu-id="cc311-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="cc311-106">Input</span></span>

### <a name="preparation--pauli"></a><span data-ttu-id="cc311-107">Hazırlık: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="cc311-107">preparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="cc311-108">Bir qubit 'in hazırlanmakta olduğu Pauli temel öğesi $P $.</span><span class="sxs-lookup"><span data-stu-id="cc311-108">The Pauli basis element $P$ in which a qubit is to be prepared.</span></span>


### <a name="measurement--pauli"></a><span data-ttu-id="cc311-109">ölçüm: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="cc311-109">measurement : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="cc311-110">Bir qubit 'in ölçülecek olan Pauli temel öğesi $Q.</span><span class="sxs-lookup"><span data-stu-id="cc311-110">The Pauli basis element $Q$ in which a qubit is to be measured.</span></span>


### <a name="channel--qubit--unit"></a><span data-ttu-id="cc311-111">Kanal: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cc311-111">channel : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="cc311-112">Tek bir qubit kanalı $ \Lambda $, davranışları işlem turununile tahmin ediliyor.</span><span class="sxs-lookup"><span data-stu-id="cc311-112">A single qubit channel $\Lambda$ whose behavior is being estimated with process tomography.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="cc311-113">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="cc311-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="cc311-114">`Zero`Olasılığa sahip sonuç $ $ \begin{hizalaması} \Pr (\Texttt{dd} | \Lambda; P, Q) = \operatorname{Tr}\left (\frac{\cıvadone + Q} {2} \Lambalo\left [\frac{\cıvadone + P} {2} \ sağ] \ sağ).</span><span class="sxs-lookup"><span data-stu-id="cc311-114">The Result `Zero` with probability $$ \begin{align} \Pr(\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left( \frac{\boldone + Q}{2} \Lambda\left[ \frac{\boldone + P}{2} \right] \right).</span></span>
<span data-ttu-id="cc311-115">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="cc311-115">\end{align} $$</span></span>

## <a name="remarks"></a><span data-ttu-id="cc311-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="cc311-116">Remarks</span></span>

<span data-ttu-id="cc311-117">Bu işlem tarafından döndürülen sonuçların üzerine dağıtım, iki-qubit durumu tomografi özel bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="cc311-117">The distribution over results returned by this operation is a special case of two-qubit state tomography.</span></span> <span data-ttu-id="cc311-118">$ \ Lambda $ için Choi – Jamiłkowski durumu $ \rho = J (\Lambda)/$2 olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="cc311-118">Let $\rho = J(\Lambda) / 2$ be the Choi–Jamiłkowski state for $\Lambda$.</span></span> <span data-ttu-id="cc311-119">Daha sonra, yukarıdaki dağıtım $ $ \begin{hizalaması} \Pr (\Texttt{dd} | \rho; ile aynıdır. M) = \operatorname{Tr} (M \rho), \end{hizalaması} $ $ burada $M = 2 (\cıvadone + P) ^ \mathrm{T}/2 \cdot (\cıvadone + Q)/$2, $P $ ve $Q $ öğesine karşılık gelen etkili ölçümdür.</span><span class="sxs-lookup"><span data-stu-id="cc311-119">Then, the distribution above is identical to $$ \begin{align} \Pr(\texttt{Zero} | \rho; M) = \operatorname{Tr}(M \rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ is the effective measurement corresponding to $P$ and $Q$.</span></span>