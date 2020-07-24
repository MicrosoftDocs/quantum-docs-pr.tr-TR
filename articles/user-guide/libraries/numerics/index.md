---
title: Kuantum Sayısal Kitaplığı Tanıtımı | Microsoft Docs
description: Kuantum Sayısal Kitaplığı Tanıtımı
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: 9552f3683e1df8cb10d19d0b3f85223df056f83d
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871357"
---
# <a name="introduction-to-the-quantum-numerics-library"></a><span data-ttu-id="fc4a8-103">Kuantum Sayısal Kitaplığı Tanıtımı</span><span class="sxs-lookup"><span data-stu-id="fc4a8-103">Introduction to the Quantum Numerics Library</span></span>

<span data-ttu-id="fc4a8-104">Birçok kuantum algoritması, matematiksel fonksiyonları girişlerin üst üste konumlandırılmasıyla değerlendiren [oracle](xref:microsoft.quantum.concepts.oracles)’ları kullanır.</span><span class="sxs-lookup"><span data-stu-id="fc4a8-104">Many quantum algorithms rely on [oracles](xref:microsoft.quantum.concepts.oracles) that evaluate mathematical functions on a superposition of inputs.</span></span>
<span data-ttu-id="fc4a8-105">Örneğin, Shor’un algoritmasının ana bileşeni, sabit bir $a$ değeri için $f(x) = a^x\operatorname{mod} N$ işlemini, $N$ değerini çarpanlarına ayırmaya yönelik sayıyı ve tüm $2n$-bit dizeleri üzerinde tekdüzen bir bindirme ile $x$ a $2n$-kubit tamsayısını değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="fc4a8-105">The main component of Shor's algorithm, for example, evaluates $f(x) = a^x\operatorname{mod} N$ for a fixed $a$, the number to factor $N$, and $x$ a $2n$-qubit integer in a uniform superposition over all $2n$-bit strings.</span></span>

<span data-ttu-id="fc4a8-106">Shor’un algoritmasını bir kuantum bilgisayarda çalıştırmak için bu fonksiyonun hedef makinenin yerel işlemlerine göre yazılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="fc4a8-106">To run Shor's algorithm on an actual quantum computer, this function has to be written in terms of the native operations of the target machine.</span></span>
<span data-ttu-id="fc4a8-107">$i$-th bit gösterilerek en önemsiz bitten saymaya başlayıp $x$ işleminin ikili gösteriminin $x_i$ ile kullanımı $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$ olarak yazılabilir.</span><span class="sxs-lookup"><span data-stu-id="fc4a8-107">Using the binary representation of $x$ with $x_i$ denoting the $i$-th bit counting from the least-significant bit, $f(x)$ can be written as $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span></span>
<span data-ttu-id="fc4a8-108">Böylece, bu $a^{2^i x_i}=(a^{2^i})^{x_i}$ işleminin koşullarının ürünü (mod N) olarak yazılabilir.</span><span class="sxs-lookup"><span data-stu-id="fc4a8-108">In turn, this can be written as a product (mod N) of terms $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span></span> <span data-ttu-id="fc4a8-109">$f(x)$ fonksiyonu, $x_iŞ işleminde koşullu öğe $a^{2^i}$ olacak şekilde $2n$ (modüler) çarpımların dizisi kullanılarak uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="fc4a8-109">The function $f(x)$ can thus be implemented using a sequence of $2n$ (modular) multiplications by $a^{2^i}$ conditional on $x_i$ being nonzero.</span></span> <span data-ttu-id="fc4a8-110">$a^{2^i}$ sabitleri önceden hesaplanabilir algoritma çalıştırılmadan önce bundan N sayısı kadar mod azaltılabilir.</span><span class="sxs-lookup"><span data-stu-id="fc4a8-110">The constants $a^{2^i}$ can be precomputed and reduced modulo N before running the algorithm.</span></span>

<span data-ttu-id="fc4a8-111">Denetimli modüler çarpımların dizisi daha da basitleştirilebilir: Her çarpım, $n$ denetimli modüler toplamalar dizisi kullanılarak gerçekleştirilebilir ve her modüler toplama normal bir toplama işlemi ve karşılaştırıcıdan oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="fc4a8-111">This sequence of controlled modular multiplications can be simplified further: Each multiplication can be performed using a sequence of $n$ controlled modular additions; and each modular addition can be built from a regular addition and a comparator.</span></span>


<span data-ttu-id="fc4a8-112">Bir uygulamaya ulaşmak için çok fazla adım gerektiğinden bu işlevlere en başta sahip olmak büyük fayda sağlar.</span><span class="sxs-lookup"><span data-stu-id="fc4a8-112">Given that so many steps are necessary to arrive at an actual implementation, it would be extremely helpful to have such functionality available from the start.</span></span>
<span data-ttu-id="fc4a8-113">Bu nedenle, Quantum Development Kit geniş bir sayısal işlev yelpazesine yönelik destek sunar.</span><span class="sxs-lookup"><span data-stu-id="fc4a8-113">This is why the Quantum Development Kit provides support for a wide range of numerics functionality.</span></span>


## <a name="functionality"></a><span data-ttu-id="fc4a8-114">İşlev</span><span class="sxs-lookup"><span data-stu-id="fc4a8-114">Functionality</span></span>

<span data-ttu-id="fc4a8-115">Şu ana kadar bahsedilen tamsayı aritmetiğinin yanı sıra sayısal kitaplık</span><span class="sxs-lookup"><span data-stu-id="fc4a8-115">Besides the integer arithmetic mentioned thus far, the numerics library provides</span></span>

- <span data-ttu-id="fc4a8-116">Giriş olarak bir veya iki kuantum tamsayının alındığı işaretli (ve işaretsiz) tamsayı işlevi (çarpma, karesini alma, kalanına bölme, evirtim...)</span><span class="sxs-lookup"><span data-stu-id="fc4a8-116">(Un)signed integer functionality (multiply, square, division with remainder, inversion, ...) with one or two quantum integer numbers as input</span></span>
- <span data-ttu-id="fc4a8-117">Giriş olarak bir veya iki kuantum tamsayının alındığı sabit nokta işlevi (ekleme / çıkarma, çarpma, karesini alma, 1/x, polinom değerlendirmesi)</span><span class="sxs-lookup"><span data-stu-id="fc4a8-117">Fixed-point functionality (add / subtract, multiply, square, 1/x, polynomial evaluation) with one or two quantum fixed-point numbers as input</span></span>

## <a name="getting-started"></a><span data-ttu-id="fc4a8-118">Başlarken</span><span class="sxs-lookup"><span data-stu-id="fc4a8-118">Getting started</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fc4a8-119">Sayısal kitaplığı kullanma hakkında bilgi edinin</span><span class="sxs-lookup"><span data-stu-id="fc4a8-119">Learn about using the numerics library</span></span>](xref:microsoft.quantum.numerics.usage)
