---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: RobustPhaseEstimation işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: d04ee578c0e6f916e9a4da451075b79e0630c70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728172"
---
# <a name="robustphaseestimation-operation"></a><span data-ttu-id="145c4-102">RobustPhaseEstimation işlemi</span><span class="sxs-lookup"><span data-stu-id="145c4-102">RobustPhaseEstimation operation</span></span>

<span data-ttu-id="145c4-103">Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="145c4-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="145c4-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="145c4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="145c4-105">, Belirli bir Oracle ve eigenstate için dayanıklı ve dayanıklı olmayan dayanıklı bir tahmin algoritması gerçekleştirir `U` ve Heisenberg sınırında varyans ölçeklendirmesiyle aşamanın gerçek değerli tek bir tahminini sağlar.</span><span class="sxs-lookup"><span data-stu-id="145c4-105">Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.</span></span>

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="145c4-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="145c4-106">Input</span></span>

### <a name="bitsprecision--int"></a><span data-ttu-id="145c4-107">bitsPrecision: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="145c4-107">bitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="145c4-108">Bu, $ \sigma \le 10,7 \pı/\Text{# sorgu} $ gibi birkaç sorgu ölçeklendirmesinin kullanıldığı standart sapma $ \sigma \ Le 2 \ pi/2 ^ \text{bitsPrecision} $ olan $ \phi $ tahminini sağlar.</span><span class="sxs-lookup"><span data-stu-id="145c4-108">This provides an estimate of $\phi$ with standard deviation $\sigma \le 2\pi / 2^\text{bitsPrecision}$ using a number of queries scaling like $\sigma \le 10.7 \pi / \text{# of queries}$.</span></span>


### <a name="oracle--discreteoracle"></a><span data-ttu-id="145c4-109">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="145c4-109">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="145c4-110">Verilen tamsayı üsleri $m $ için $U ^ d $ uygulayan bir işlem.</span><span class="sxs-lookup"><span data-stu-id="145c4-110">An operation implementing $U^m$ for given integer powers $m$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="145c4-111">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="145c4-111">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="145c4-112">$U $ ' nin üzerinde hareket eden bir hisse kaydı.</span><span class="sxs-lookup"><span data-stu-id="145c4-112">A quantum register that $U$ acts on.</span></span> <span data-ttu-id="145c4-113">Bu bir eigenstate $ \ket{\phi} $ of $U $, sonra $ \phi\in (-\pı, \pı] $ için bilinmeyen bir aşama olan \ket{\phi} = e ^ {i\phi} \ket{\phi} $ öğesini $U.</span><span class="sxs-lookup"><span data-stu-id="145c4-113">If it stores an eigenstate $\ket{\phi}$ of $U$, then $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi\in(-\pi,\pi]$ an unknown phase.</span></span>



## <a name="output--double"></a><span data-ttu-id="145c4-114">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="145c4-114">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="145c4-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="145c4-115">Remarks</span></span>

<span data-ttu-id="145c4-116">Çok sayıda sorgu sınırında, $ \phi $ ile ilgili $ \sigma \ GE 2 \pı/\Text{# sorgu} $ tahmininin standart sapması için alt sınır Cramer-Rao.</span><span class="sxs-lookup"><span data-stu-id="145c4-116">In the limit of a large number of queries, Cramer-Rao lower bounds for the standard deviation of the estimate of $\phi$ satisfy $\sigma \ge 2 \pi / \text{# of queries}$.</span></span>

## <a name="references"></a><span data-ttu-id="145c4-117">Referanslar</span><span class="sxs-lookup"><span data-stu-id="145c4-117">References</span></span>

- <span data-ttu-id="145c4-118">Kımel, Guang Hao Low, Theodore J. Yoder tarafından sağlam aşama tahmini aracılığıyla bir evrensel Single-Qubit Gate-Set sağlam ayarı https://arxiv.org/abs/1502.02677</span><span class="sxs-lookup"><span data-stu-id="145c4-118">Robust Calibration of a Universal Single-Qubit Gate-Set via Robust Phase Estimation Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span></span>