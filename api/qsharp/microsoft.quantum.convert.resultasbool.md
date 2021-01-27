---
uid: Microsoft.Quantum.Convert.ResultAsBool
title: ResultAsBool işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultAsBool
qsharp.summary: Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 9de7ca64992e0a4d73c1d00218b3eab4ab545a1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832555"
---
# <a name="resultasbool-function"></a><span data-ttu-id="00b94-102">ResultAsBool işlevi</span><span class="sxs-lookup"><span data-stu-id="00b94-102">ResultAsBool function</span></span>

<span data-ttu-id="00b94-103">Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="00b94-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="00b94-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="00b94-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="00b94-105">Bir `Result` türü `Bool` türüne dönüştürür; burada `One` eşlenir ve ile `true` `Zero` eşlenir `false` .</span><span class="sxs-lookup"><span data-stu-id="00b94-105">Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultAsBool (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="00b94-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="00b94-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="00b94-107">Giriş: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="00b94-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="00b94-108">`Result` dönüştürülecek.</span><span class="sxs-lookup"><span data-stu-id="00b94-108">`Result` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="00b94-109">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="00b94-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="00b94-110">Öğesini `Bool` temsil eden `input` .</span><span class="sxs-lookup"><span data-stu-id="00b94-110">A `Bool` representing the `input`.</span></span>