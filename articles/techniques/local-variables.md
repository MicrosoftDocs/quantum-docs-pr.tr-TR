---
title: 'S # teknikleri-yerel değişkenler | Microsoft Docs'
description: Q. Teknik-yerel değişkenler
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4f5eff1ee8482fa5e5fee9dff421efab93fc0c5a
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183293"
---
# <a name="local-variables"></a><span data-ttu-id="951a7-103">Yerel değişkenler</span><span class="sxs-lookup"><span data-stu-id="951a7-103">Local Variables</span></span> #

<span data-ttu-id="951a7-104">Q # içindeki herhangi bir türün değeri, `let` anahtar sözcüğü kullanılarak bir işlem veya işlev içinde yeniden kullanım için bir değişkene atanabilir.</span><span class="sxs-lookup"><span data-stu-id="951a7-104">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>
<span data-ttu-id="951a7-105">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="951a7-105">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="951a7-106">Bu, belirli bir Pauli işleçleri dizisini `measurementOperator`adlı bir değişkene atar.</span><span class="sxs-lookup"><span data-stu-id="951a7-106">This assigns a particular array of Pauli operators to a variable called `measurementOperator`.</span></span>

> [!TIP]
> <span data-ttu-id="951a7-107">`let` deyiminin sağ tarafındaki ifade belirsiz olduğundan ve tür derleyicinin tarafından çıkarsandığı için yeni değişkenimizin türünü açık bir şekilde belirtmemiz gerekmediğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="951a7-107">Note that we did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="951a7-108">Q # içindeki değişkenler *sabittir*, yani bir değişken bu şekilde tanımlandığında, artık hiçbir şekilde değiştirilemez.</span><span class="sxs-lookup"><span data-stu-id="951a7-108">Variables in Q# are *immutable*, meaning that once a variable has been defined in this way, it can no longer be changed in any way.</span></span>
<span data-ttu-id="951a7-109">Bu, bir işlemin `Adjoint` türevini uygulamak için değişkenlerin yeniden düzenlenmesine yönelik klasik mantığın iyileştirilmesi dahil olmak üzere birkaç yarar iyileştirmesi sağlar.</span><span class="sxs-lookup"><span data-stu-id="951a7-109">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

<span data-ttu-id="951a7-110">Yukarıdaki `let` bağlama kullanılarak tanımlanan değişkenler, bir işlemin gövdesi veya bir `for` döngüsünün içeriği gibi belirli bir kapsamda yereldir.</span><span class="sxs-lookup"><span data-stu-id="951a7-110">Variables defined using the `let` binding as above are local to a particular scope, such as the body of an operation or the contents of a `for` loop.</span></span>


## <a name="mutability"></a><span data-ttu-id="951a7-111">Değişebilirliği</span><span class="sxs-lookup"><span data-stu-id="951a7-111">Mutability</span></span> ##

<span data-ttu-id="951a7-112">`let`ile bir değişken oluşturulmasına alternatif olarak, `mutable` anahtar sözcüğü, ilk kez `set` anahtar sözcüğü kullanılarak oluşturulduktan sonra yeniden bağlanabilen özel bir kesilebilir değişken oluşturur.</span><span class="sxs-lookup"><span data-stu-id="951a7-112">As an alternative to creating a variable with `let`, the `mutable` keyword will create a special mutable variable that can be re-bound after it is initially created by using the `set` keyword.</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

<span data-ttu-id="951a7-113">Tüm Q # türleri diziler de dahil olmak üzere değer semantiğini izler.</span><span class="sxs-lookup"><span data-stu-id="951a7-113">All types in Q#, including arrays, follow value semantics.</span></span> <span data-ttu-id="951a7-114">Özellikle, dizi öğelerini güncelleştirmek mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="951a7-114">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="951a7-115">Var olan bir diziyi değiştirmek için, içindeki F#kayıtlar için bir kopyalama ve güncelleştirme mekanizmasından çok daha fazla yararlanmak gerekir.</span><span class="sxs-lookup"><span data-stu-id="951a7-115">To modify an existing array requires leveraging a copy-and-update mechanism much like the one for records in F#.</span></span> <span data-ttu-id="951a7-116">[`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays)sağlanan diziler için kitaplık araçlarını kullanarak, Dizin `i` 'nin verilen değeri aldığı ve diğer tüm girdilerin kimlik olduğu Paulis dizisini döndüren bir işlevi kolayca tanımlayabiliriz:</span><span class="sxs-lookup"><span data-stu-id="951a7-116">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can e.g. easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity:</span></span> 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

<span data-ttu-id="951a7-117">Q # deyimlerini ve ifadelerini ele alırken dizilerle nasıl çalışacağız hakkında daha fazla bilgi göndereceğiz.</span><span class="sxs-lookup"><span data-stu-id="951a7-117">We will elaborate more on how to work with arrays when discussing Q# statements and expressions.</span></span> 

<span data-ttu-id="951a7-118">Q # içindeki değiştirici, bir tür veya değer yerine bir *sembol* için geçerli olan bir kavramdır.</span><span class="sxs-lookup"><span data-stu-id="951a7-118">Mutability within Q# is a concept that applies to a *symbol* rather than a type or value.</span></span> <span data-ttu-id="951a7-119">Özellikle, tür sisteminde bir gösterimi yoktur, örtük olarak veya açıkça ve bir bağlamanın değişebilir (`mutable` anahtar sözcüğüyle gösterildiği gibi) veya sabit (`let`tarafından belirtildiği gibi), bağlama değişkenlerinin türünü değiştirmez.</span><span class="sxs-lookup"><span data-stu-id="951a7-119">Specifically, it does not have a representation in the type system, implicitly or explicitly, and whether or not a binding is mutable (as indicated by the `mutable` keyword) or immutable (as indicated by `let`) does not change the type of the bound variable(s).</span></span> <span data-ttu-id="951a7-120">Bu, özelleştirilmiş işlevler ve işlemler içindeki değiştirici yalıtmak için önemli bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="951a7-120">This provides an important way to isolate mutability inside specialized functions and operations.</span></span>
<span data-ttu-id="951a7-121">Özellikle, kesilebilir değişken kullanan bir işlem için adjoint özelleştirmesi otomatik olarak üretilemez olsa da, otomatik oluşturma, değiştirici kullanan bir işlev çağıran bir işlem için sorunsuz çalışır.</span><span class="sxs-lookup"><span data-stu-id="951a7-121">In particular, even though an adjoint specialization for an operation which uses a mutable variable cannot be auto-generated, auto-generation works fine for an operation calling a function which uses mutability.</span></span>
<span data-ttu-id="951a7-122">Bu nedenle, daha kısa ve sıkıştır kullanan işlevleri ve işlemleri mümkün olduğunca kısa ve küçük bir hale getirmek iyi bir uygulamadır, böylece hisse programının kalanı sıradan sabit değişkenler kullanılarak yazılabilir.</span><span class="sxs-lookup"><span data-stu-id="951a7-122">For this reason, it is a good practice to make functions and operations which use mutability as short and compact as possible, so that the rest of the quantum program can be written using ordinary immutable variables.</span></span>


## <a name="deconstruction"></a><span data-ttu-id="951a7-123">Ayrıştırma</span><span class="sxs-lookup"><span data-stu-id="951a7-123">Deconstruction</span></span> ##

<span data-ttu-id="951a7-124">Tek bir değişken atamaya ek olarak, `let` ve `mutable` anahtar sözcükleri; diğer tüm bağlama yapısıyla aynı zamanda bir [demet türünün](xref:microsoft.quantum.language.type-model#tuple-types)içeriğinin açılmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="951a7-124">In addition to assigning a single variable, the `let` and `mutable` keywords - or in fact any other binding construct - also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.language.type-model#tuple-types).</span></span>
<span data-ttu-id="951a7-125">Bu formun bir ataması, bu kayıt düzeninin öğelerini *parçalara ayırmayı* kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="951a7-125">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>
<span data-ttu-id="951a7-126">Örneğin, bir Hamiltonian içindeki bir terimi bir tanımlama grubu tarafından modelliyoruz, bu terimin altında benzetim yapmanız gereken farklı verilere erişmek için oluşturmayı kullanabiliriz:</span><span class="sxs-lookup"><span data-stu-id="951a7-126">For instance, if we model a term in a Hamiltonian by a tuple, then we can use deconstruction to access the different data that we need to simulate under that term:</span></span>

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


