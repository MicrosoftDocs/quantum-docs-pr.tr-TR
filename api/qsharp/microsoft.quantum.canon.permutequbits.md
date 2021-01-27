---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: Permütasyon Tequbits işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 2fbbe0d99ad1383d77cb08ff6b03bcebd8a1971f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852336"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="42583-102">Permütasyon Tequbits işlemi</span><span class="sxs-lookup"><span data-stu-id="42583-102">PermuteQubits operation</span></span>

<span data-ttu-id="42583-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="42583-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="42583-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="42583-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="42583-105">DEĞIŞTIRME işlemini kullanarak permütasyon qutes.</span><span class="sxs-lookup"><span data-stu-id="42583-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="42583-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="42583-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="42583-107">sıralama: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="42583-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="42583-108">Qubits 'in, bu dizindeki qubit 'in Şu anda [i] sıralamada olacağı yeni sıralamasını açıklar.</span><span class="sxs-lookup"><span data-stu-id="42583-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="42583-109">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="42583-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="42583-110">Üzerinde işlem yapmak için qubit kaydolun.</span><span class="sxs-lookup"><span data-stu-id="42583-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="42583-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="42583-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="42583-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="42583-112">Example</span></span>

<span data-ttu-id="42583-113">Verilen sıralama = [2, 1, 0] ve Register $ \ket{\ alpha_0} \ket{\ alpha_1} \ket{\ alpha_2} $, permütasyon Tequbits kaydı $ \ket{\ alpha_2} \ket{\ alpha_1} \ket{\ alpha_0} $ olarak değiştiriyor</span><span class="sxs-lookup"><span data-stu-id="42583-113">Given ordering = [2, 1, 0] and register $\ket{\alpha_0} \ket{\alpha_1} \ket{\alpha_2}$, PermuteQubits changes the register into $\ket{\alpha_2} \ket{\alpha_1} \ket{\alpha_0}$</span></span>

```qsharp
// The following two lines are equivalent
PermuteQubits([2, 1, 0], register);
SWAP(register[0], register[2]);
```