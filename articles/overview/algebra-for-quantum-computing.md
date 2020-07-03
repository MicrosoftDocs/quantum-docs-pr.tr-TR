---
title: Kuantum bilişimi için doğrusal cebir
description: Kuantum bilişimini anlamak için gereken temel doğrusal cebir kavramlarını öğrenme
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.algebra
ms.openlocfilehash: 4cf6cce870c7661a7fffc21dcb60dd53cf281ddd
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415464"
---
# <a name="linear-algebra-for-quantum-computing"></a>Kuantum bilişimi için doğrusal cebir

Doğrusal cebir, kuantum bilişiminin dilidir. Kuantum programları uygulamak veya yazmak için bunu bilmeniz gerekmese de, doğrusal cebir genellikle kubit durumları ile kuantum işlemlerini açıklamak ve kuantum bilgisayarın bir dizi yönergeye yanıt olarak ne yapacağını tahmin etmek için yaygın olarak kullanılır.

[Kuantum fiziğinin temel kavramlarına](xref:microsoft.quantum.overview.understanding) aşina olmanın kuantum bilişimini anlamanıza yardımcı olması gibi, bazı temel doğrusal cebir bilgilerine sahip olmak da kuantum algoritmalarının nasıl çalıştığını anlamanıza yardımcı olabilir. En azından, **vektörler** ve **matris çarpımı** hakkında bilgi sahibi olmanız gerekir. Bu cebir kavramlarıyla ilgili bilgilerinizi tazelemeniz gerekiyorsa temel bilgileri kapsayan bazı öğreticiler aşağıda verilmiştir:

- [Doğrusal cebir hakkında Jupyter not defteri öğreticisi](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)
- [Karmaşık aritmetik hakkında Jupyter not defteri öğreticisi](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)
- [Kuantum Hesaplama için Doğrusal Cebir](https://cds.cern.ch/record/1522001/files/978-1-4614-6336-8_BookBackMatter.pdf)
- [Doğrusal Cebir ile İlgili Temel Bilgiler](https://www.math.ubc.ca/~carrell/NB.pdf)
- [Kuantum Hesaplama El Kitabı](https://www.codeproject.com/Articles/5155638/Quantum-Computation-Primer-Part-1#exploring-quantum-superposition)

## <a name="vectors-and-matrices-in-quantum-computing"></a>Kuantum bilişiminde vektörler ve matrisler

[Kuantum bilişimini anlama](xref:microsoft.quantum.overview.understanding) konusunda, bir kubitin 1 veya 0 durumunda ya da bir süper konum veya her ikisinde olduğunu gördünüz. Doğrusal cebir kullanılarak bir kubitin durumu, vektör olarak tanımlanır ve tek sütunlu **matris** $\begin{bmatrix} a \\\\  b \end{bmatrix}$ ile temsil edilir. Bu ayrıca **kuantum durum vektörü** olarak da bilinir ve $|a|^2 + |b|^2 = 1$ gereksinimini karşılamalıdır.  

Matrisin öğeleri kubitin, $|a|^2$ öğesinin sıfıra çökme olasılığı ve $|b|^2$ öğesinin bire çökme olasılığı olduğu iki durumdan birine çökme olasılığını temsil eder. Aşağıdaki matrislerin tümü, geçerli kuantum durum vektörlerini temsil eder:

$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}, \begin{bmatrix} 0 \\\\  1 \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix} \text{ ve }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}.$$

[Kuantum bilgisayarlar ve kuantum simülatörleri](xref:microsoft.quantum.overview.simulators) konusunda, kuantum işlemlerinin bir kubitin durumunu değiştirmek için kullanıldığını da gördünüz.  Kuantum işlemleri bir matris ile de gösterilebilir. Bir kuantum işlemi bir kubite uygulandığında, bunları temsil eden iki matris çarpılır ve elde edilen yanıt, kubitin işlemden sonraki yeni durumunu temsil eder.  

Matris çarpımı ile temsil edilen iki yaygın kuantum işlemi aşağıda verilmiştir.


[`X` işlemi](xref:microsoft.quantum.intrinsic.x), Pauli matrisi $X$,

$$X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix},$$
    
ile temsil edilir ve bir kubitin durumunu 0'dan 1'e (veya tam tersi) çevirmek için kullanılır. Örneğin,

$$\begin{bmatrix}0 &1\\\\ 1 &0\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}.$$

['H' işlemi](xref:microsoft.quantum.intrinsic.h), Hadamard dönüştürme $H$,

$$H = \dfrac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix},$$

 ile temsil edilir ve burada gösterildiği gibi, bir kubiti her iki duruma da çökme olasılığı olan bir süper konum durumuna sokar

$$\frac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix}=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=\left(\frac{1}{\sqrt{2}}\right)^2=\frac{1}{2}.$$

Bir kuantum işlemini temsil eden matrisin tek bir gereksinimi vardır: Bir **birim** matris olmalıdır. Matrisin **tersi**, matrisin **eşlenik devriğine** eşitse bu bir birim matristir.

## <a name="representing-two-qubit-states"></a>İki kubitli durumları temsil etme

Yukarıdaki örneklerde, bir kubitin durumu, tek sütunlu bir matris olan $\begin{bmatrix} a \\\\  b \end{bmatrix}$ kullanılarak açıklandı ve buna bir işlemin uygulanması iki matrisin çarpılmasıyla açıklandı. Ancak kuantum bilgisayarlar birden fazla kubit kullanır, o halde iki kubitin birleşik durumunu nasıl açıklarsınız? 

Her kubitin bir vektör alanı olduğunu ve bu nedenle doğrudan çarpılamayacaklarını unutmayın. Bunun yerine, ayrı ayrı vektör alanlarından yeni bir vektör alanı oluşturan ve $\otimes$ sembolüyle temsil edilen ilgili bir işlem olan **tensör çarpımını** kullanırsınız. Örneğin, iki kubit durumunun tensör çarpımı olan $\begin{bmatrix} a \\\\  b \end{bmatrix}$ ve $\begin{bmatrix} c \\\\  d \end{bmatrix}$ hesaplanır

$$ \begin{bmatrix} a \\\\  b \end{bmatrix} \otimes \begin{bmatrix} c \\\\  d \end{bmatrix} =\begin{bmatrix} a \begin{bmatrix} c \\\\  d \end{bmatrix} \\\\ b \begin{bmatrix}c \\\\  d \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}. $$

Sonuç, her öğenin bir olasılığı temsil ettiği dört boyutlu bir matristir. Örneğin, $ac$, iki kubitin 0 ve 0 değerine çökmesi olasılığıdır, $ad$ ise 0 ve 1 olasılığıdır ve bu şekilde devam eder. 

Tek bir $\begin{bmatrix} a \\\\  b \end{bmatrix}$ kubit durumunun bir kuantum durumunu temsil etmesi için $|a|^2 + |b|^2 = 1$ gereksinimini karşılaması gerektiği gibi, $\begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}$ iki kubitli durumunun da $|ac|^2 + |ad|^2 + |bc|^2+ |bd|^2 = 1$ gereksinimini karşılaması gerekir.

## <a name="summary"></a>Özet

Doğrusal cebir, kuantum bilişimini ve kuantum fiziğini açıklamaya yönelik standart dildir. Microsoft Quantum geliştirme setine dahil edilen [kitaplıklar](xref:microsoft.quantum.libraries), temel alınan matematiğin anlaşılmasına gerek kalmadan gelişmiş kuantum algoritmaları çalıştırmanıza yardımcı olsa da, temel bilgileri anlamak hızlı bir şekilde başlamanızı ve bundan sonra yapacağınız işlemleri sağlam bir temele oturtmanızı sağlar.

## <a name="next-steps"></a>Sonraki adımlar

[QDK’yı yükleme](xref:microsoft.quantum.install)
