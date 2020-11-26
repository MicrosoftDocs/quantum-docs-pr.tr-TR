---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: Hazırlık Esingliqubitişdentity işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 1c8c161ec2eae73a81c46e7941af49145cde0493
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193633"
---
# <a name="preparesinglequbitidentity-operation"></a><span data-ttu-id="e8d49-102">Hazırlık Esingliqubitişdentity işlemi</span><span class="sxs-lookup"><span data-stu-id="e8d49-102">PrepareSingleQubitIdentity operation</span></span>

<span data-ttu-id="e8d49-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e8d49-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e8d49-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e8d49-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e8d49-105">Yüksek ölçüde karışık durumda bir qubit hazırlar.</span><span class="sxs-lookup"><span data-stu-id="e8d49-105">Prepares a qubit in the maximally mixed state.</span></span>

<span data-ttu-id="e8d49-106">$/Boldo/$2 durumunda verilen qubit $ $ \begin{hizalaması} \Omega (\rho) \mathrel{: =} \frac {1} {4} \ sum_ {\mu \{ \0 ' ı uygulayarak verilen qubit 'i hazırlar 1, 2, 3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\leger}, \end{hizalaması} $ $; $ \sigma \_ i $, $i $ TH Pauli işleci, ve $ \rho $, karışık bir durumu temsil eden bir yoğunluk operatöründür.</span><span class="sxs-lookup"><span data-stu-id="e8d49-106">It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.</span></span>

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e8d49-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="e8d49-107">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="e8d49-108">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e8d49-108">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e8d49-109">Durumu yukarıda açıklanan şekilde depolarized bir qubit.</span><span class="sxs-lookup"><span data-stu-id="e8d49-109">A qubit whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e8d49-110">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e8d49-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e8d49-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e8d49-111">Remarks</span></span>

<span data-ttu-id="e8d49-112">Bu işlemi bir duruma uygulamanın sonucunu açıklayan karışık durum $ \ cıvadone/$2, bu işlemde yapılan rastgele seçimler üzerinde bir beklentideğeri örtülü olarak tanımlar.</span><span class="sxs-lookup"><span data-stu-id="e8d49-112">The mixed state $\boldone / 2$ describing the result of applying this operation to a state implicitly describes an expectation value over random choices made in this operation.</span></span>
<span data-ttu-id="e8d49-113">Bu nedenle, tek bir uygulama için, bu işlem saf durumları saf durumlara eşler, ancak beklentide anlatıldığı gibi davranır.</span><span class="sxs-lookup"><span data-stu-id="e8d49-113">Thus, for any single application, this operation maps pure states to pure states, but it acts as described in expectation.</span></span>
<span data-ttu-id="e8d49-114">Özellikle, bu işlem, bir kanalın olmayan bileşenlerini ölçmek için işlem *turuntografda* kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="e8d49-114">In particular, this operation can be used in process tomography to measure the *non-unital* components of a channel.</span></span>