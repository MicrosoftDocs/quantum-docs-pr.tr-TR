---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Prepareıdentity işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: ec7e813110ccd9e6d499fc469fa27249a182b870
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855884"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="43e1a-102">Prepareıdentity işlemi</span><span class="sxs-lookup"><span data-stu-id="43e1a-102">PrepareIdentity operation</span></span>

<span data-ttu-id="43e1a-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="43e1a-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="43e1a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="43e1a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="43e1a-105">Kayıt verildiğinde, bu kaydı, en yüksek düzeyde karışık durumda hazırlar.</span><span class="sxs-lookup"><span data-stu-id="43e1a-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="43e1a-106">Kayıt, her bir qubit 'e tüm depolarizing kanalını uygulayarak $ \ cıvadone/2 ^ N $ durumunda hazırlandı; burada $N $ kaydın uzunluğudur.</span><span class="sxs-lookup"><span data-stu-id="43e1a-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="43e1a-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="43e1a-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="43e1a-108">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="43e1a-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="43e1a-109">Durumu yukarıda açıklanan şekilde depolarized olan bir kayıt.</span><span class="sxs-lookup"><span data-stu-id="43e1a-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="43e1a-110">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="43e1a-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="43e1a-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="43e1a-111">See Also</span></span>

- [<span data-ttu-id="43e1a-112">Microsoft. hisse. hazırlık. hazırlık Esingliqubitişdentity</span><span class="sxs-lookup"><span data-stu-id="43e1a-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)