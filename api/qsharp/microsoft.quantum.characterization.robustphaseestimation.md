---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: RobustPhaseEstimation işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: 4b37c8275a5b2aee8534bacc5831281aa498b57d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851794"
---
# <a name="robustphaseestimation-operation"></a><span data-ttu-id="66aaa-102">RobustPhaseEstimation işlemi</span><span class="sxs-lookup"><span data-stu-id="66aaa-102">RobustPhaseEstimation operation</span></span>

<span data-ttu-id="66aaa-103">Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="66aaa-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="66aaa-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="66aaa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="66aaa-105">, Belirli bir Oracle ve eigenstate için dayanıklı ve dayanıklı olmayan dayanıklı bir tahmin algoritması gerçekleştirir `U` ve Heisenberg sınırında varyans ölçeklendirmesiyle aşamanın gerçek değerli tek bir tahminini sağlar.</span><span class="sxs-lookup"><span data-stu-id="66aaa-105">Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.</span></span>

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="66aaa-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="66aaa-106">Input</span></span>

### <a name="bitsprecision--int"></a><span data-ttu-id="66aaa-107">bitsPrecision: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="66aaa-107">bitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="66aaa-108">Bu, $ \sigma \le 10,7 \pı/\Text{# sorgu} $ gibi birkaç sorgu ölçeklendirmesinin kullanıldığı standart sapma $ \sigma \ Le 2 \ pi/2 ^ \text{bitsPrecision} $ olan $ \phi $ tahminini sağlar.</span><span class="sxs-lookup"><span data-stu-id="66aaa-108">This provides an estimate of $\phi$ with standard deviation $\sigma \le 2\pi / 2^\text{bitsPrecision}$ using a number of queries scaling like $\sigma \le 10.7 \pi / \text{# of queries}$.</span></span>


### <a name="oracle--discreteoracle"></a><span data-ttu-id="66aaa-109">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="66aaa-109">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="66aaa-110">Verilen tamsayı üsleri $m $ için $U ^ d $ uygulayan bir işlem.</span><span class="sxs-lookup"><span data-stu-id="66aaa-110">An operation implementing $U^m$ for given integer powers $m$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="66aaa-111">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="66aaa-111">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="66aaa-112">$U $ ' nin üzerinde hareket eden bir hisse kaydı.</span><span class="sxs-lookup"><span data-stu-id="66aaa-112">A quantum register that $U$ acts on.</span></span> <span data-ttu-id="66aaa-113">Bu bir eigenstate $ \ket{\phi} $ of $U $, sonra $ \phi\in (-\pı, \pı] $ için bilinmeyen bir aşama olan \ket{\phi} = e ^ {i\phi} \ket{\phi} $ öğesini $U.</span><span class="sxs-lookup"><span data-stu-id="66aaa-113">If it stores an eigenstate $\ket{\phi}$ of $U$, then $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi\in(-\pi,\pi]$ an unknown phase.</span></span>



## <a name="output--double"></a><span data-ttu-id="66aaa-114">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="66aaa-114">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="66aaa-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="66aaa-115">Remarks</span></span>

<span data-ttu-id="66aaa-116">Çok sayıda sorgu sınırında, $ \phi $ ile ilgili $ \sigma \ GE 2 \pı/\Text{# sorgu} $ tahmininin standart sapması için alt sınır Cramer-Rao.</span><span class="sxs-lookup"><span data-stu-id="66aaa-116">In the limit of a large number of queries, Cramer-Rao lower bounds for the standard deviation of the estimate of $\phi$ satisfy $\sigma \ge 2 \pi / \text{# of queries}$.</span></span>

## <a name="references"></a><span data-ttu-id="66aaa-117">Başvurular</span><span class="sxs-lookup"><span data-stu-id="66aaa-117">References</span></span>

- <span data-ttu-id="66aaa-118">Kımel, Guang Hao Low, Theodore J. Yoder tarafından sağlam aşama tahmini aracılığıyla bir evrensel Single-Qubit Gate-Set sağlam ayarı https://arxiv.org/abs/1502.02677</span><span class="sxs-lookup"><span data-stu-id="66aaa-118">Robust Calibration of a Universal Single-Qubit Gate-Set via Robust Phase Estimation Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span></span>