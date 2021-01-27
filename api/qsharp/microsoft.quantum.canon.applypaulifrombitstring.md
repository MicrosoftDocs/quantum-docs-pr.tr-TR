---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: Applypauömrü Rombitstring işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: e0edd8420127339116e525421ba23e246dcf0a45
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841584"
---
# <a name="applypaulifrombitstring-operation"></a><span data-ttu-id="c3f46-102">Applypauömrü Rombitstring işlemi</span><span class="sxs-lookup"><span data-stu-id="c3f46-102">ApplyPauliFromBitString operation</span></span>

<span data-ttu-id="c3f46-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c3f46-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c3f46-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c3f46-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c3f46-105">Bir Boolean dizisinin karşılık gelen biti verilen bir girişle eşleşiyorsa, dizideki her bir qubit üzerinde Pauli işleci uygular.</span><span class="sxs-lookup"><span data-stu-id="c3f46-105">Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.</span></span>

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c3f46-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c3f46-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="c3f46-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="c3f46-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="c3f46-108">Nereye uygulanacak Pauli işleci `qubits[idx]``bitsApply == bits[idx]`</span><span class="sxs-lookup"><span data-stu-id="c3f46-108">Pauli operator to apply to `qubits[idx]` where `bitsApply == bits[idx]`</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="c3f46-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c3f46-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c3f46-110">bit Bu değer ise Pauli Uygula</span><span class="sxs-lookup"><span data-stu-id="c3f46-110">apply Pauli if bit is this value</span></span>


### <a name="bits--bool"></a><span data-ttu-id="c3f46-111">bit: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="c3f46-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="c3f46-112">İçinde hangi karşılık gelen qubitin çalışılmalıdır belirten Boole kaydı `qubits`</span><span class="sxs-lookup"><span data-stu-id="c3f46-112">Boolean register specifying which corresponding qubit in `qubits` should be operated on</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="c3f46-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c3f46-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c3f46-114">Belirtilen Pauli işlecinin seçmeli olarak uygulanacağı hisse kayıt</span><span class="sxs-lookup"><span data-stu-id="c3f46-114">Quantum register on which to selectively apply the specified Pauli operator</span></span>



## <a name="output--unit"></a><span data-ttu-id="c3f46-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3f46-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c3f46-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c3f46-116">Remarks</span></span>

<span data-ttu-id="c3f46-117">Boole dizisi ve hisse kayıt uzunluğu eşit olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="c3f46-117">The Boolean array and the quantum register must be of equal length.</span></span>