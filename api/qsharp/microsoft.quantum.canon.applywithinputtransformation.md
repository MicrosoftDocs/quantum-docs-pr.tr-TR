---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: Applywithınputtransformation işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: d4589acbe9f9dc6c6ab665582ed663dbc193edbb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850369"
---
# <a name="applywithinputtransformation-operation"></a><span data-ttu-id="e3d3c-102">Applywithınputtransformation işlemi</span><span class="sxs-lookup"><span data-stu-id="e3d3c-102">ApplyWithInputTransformation operation</span></span>

<span data-ttu-id="e3d3c-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e3d3c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e3d3c-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e3d3c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e3d3c-105">Bazı girişleri kabul eden bir işlem, bu işlemle uyumlu bir çıkış döndüren bir işlev ve bu işleve bir giriş verildiğinde, girişi işlemin beklenen bir biçime dönüştürmek için işlevini kullanarak işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="e3d3c-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="e3d3c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e3d3c-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="e3d3c-107">FN: ' U-> 'T</span><span class="sxs-lookup"><span data-stu-id="e3d3c-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="e3d3c-108">Verilen girişi işlem tarafından beklenen bir biçimde dönüştüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="e3d3c-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="e3d3c-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e3d3c-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e3d3c-110">Uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="e3d3c-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="e3d3c-111">Giriş: ' U</span><span class="sxs-lookup"><span data-stu-id="e3d3c-111">input : 'U</span></span>

<span data-ttu-id="e3d3c-112">İşleve bir giriş.</span><span class="sxs-lookup"><span data-stu-id="e3d3c-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e3d3c-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e3d3c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e3d3c-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="e3d3c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e3d3c-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="e3d3c-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="e3d3c-116">' U</span><span class="sxs-lookup"><span data-stu-id="e3d3c-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="e3d3c-117">Örnek</span><span class="sxs-lookup"><span data-stu-id="e3d3c-117">Example</span></span>

<span data-ttu-id="e3d3c-118">Aşağıdaki çağrı, @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" @"Microsoft.Quantum.Arithmetic.BigEndian" türünde bir girişe giriş için tasarlanan bir işlemi uygulamak için kullanır @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="e3d3c-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="e3d3c-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e3d3c-119">See Also</span></span>

- [<span data-ttu-id="e3d3c-120">Microsoft. hisse. Canon. Applywithınputtransform Tiona</span><span class="sxs-lookup"><span data-stu-id="e3d3c-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="e3d3c-121">Microsoft. hisse. Canon. Applywithınputtransform Tionc</span><span class="sxs-lookup"><span data-stu-id="e3d3c-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="e3d3c-122">Microsoft. hisse. Canon. Applywithınputtransform Tionca</span><span class="sxs-lookup"><span data-stu-id="e3d3c-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="e3d3c-123">Microsoft. hisse. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="e3d3c-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)