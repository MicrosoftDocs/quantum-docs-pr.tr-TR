---
title: Elektronik sistemler için hisse modelleri | Microsoft Docs
description: Elektronik sistemler için hisse modelleri kavramsal belgeleri
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantummodels
ms.openlocfilehash: 45d134333c8a3c8937d206cb0a4a9cc6101a85df
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184160"
---
# <a name="quantum-models-for-electronic-systems"></a>Elektronik sistemler için hisse modelleri

Elektronik sistemlerin benzetimini yapmak için önce, yukarıda açıklanan kurallı bir işlem yordamıyla bulunabilir Hamiltonian 'yi belirterek başladık.
Özellikle, momenta $p _i $ (üç boyutta) ile $N _E $ elektriklerinin yanı sıra vektör $m _E $ ve konum vektörlerini $Z $x _K $. konumlarda $y _K $ $ ile \hat{H}), Bmiltonian işleci, \begin{Equation} = \sum\_{ı = 1} ^ {N @no_ _t_1_ e} \frac{\hat{p}\_i ^ 2} {2m\_e} + \frac{1}{2}\sum\_{i\ne j} \frac{e ^ 2} {| \hat{x}\_ı-\hat{x}\_j |}-\sum\_{ı , k} \frac{Z\_ke ^ 2} {| \hat{x}\_i-{y}\_k |} + \frac{1}{2} \sum_{k\ne k '} \frac{Z\_kZ\_{k '} e ^ 2} {| y\_k-y\_k ' |}. \label{EQ: ham} \end{Equation} momenta işleçleri $ \hat{p}\_i ^ 2 $, gerçek alanda Laplacıa işleçleri olarak görüntülenebilir, yani $ \hat{p}\_i ^ 2 =-\partial\_{x\_ı} ^ 2-\partial\_{y\_i} ^ 2-\ kısmi\_{z\_i} ^ 2 $.
Burada, nucleı 'nin moleule için geri kalanı olduğunu basitleştirecek şekilde yaptık.
Bu, Perceterpenheimer yaklaşık olarak bilinir ve, elektron kütle yaklaşık $1/1836 $ prototipn 'ın kütle olduğundan, $ \hat{H} $ düşük enerji enerji yelpazesi için geçerli olduğunu eğilimi gösterir.
Bu Hamiltonian operatörü, $N\_e $ elektriklerini bir sistem için enerji yazarak ve [hisse](xref:microsoft.quantum.chemistry.concepts.quantumdynamics)malarca açıklanan kurallı ölçü sürecini uygulayarak kolayca bulunabilir.

$E ^ {-i\hat {H} t} $ için Unitary matris gösterimini oluşturmak için, matris olarak $ \hat{H} $ işlecini temsil etmemiz gerekir.
Bunun için, içindeki sorunu temsil eden bir koordinat sistemi veya temeli seçmemiz gerekir.
Örneğin, $ \psi_j $, $N _E $ elektriler için dikgen bir temel işlevler kümesi ise, matrisi tanımlayabiliriz

\begin{Equation} H\_{i, j} = \int\_{-\infty} ^ \infty\int\_{-\infty} ^ \Infı\hat{H} \ PSI ^ {\*}\_i (x\_1) \psi\_j (x\_2) \gg ^ 3x\_1 \gg ^ 3x\_2. \ etiket {EQ: discreteHam} \end{Equation}

Prensibi, $ \hat{H} $ işlecinin sınırsız olduğu ve sonlu bir boyut alanı üzerinde işlem yapması durumunda, öğe içeren matris $H\_\{i, j\}$ üzerinde.
Bu, bir taban kümesinin çok küçük olarak seçilmesinde hataların tahakkuk etmesidir. Ancak, büyük bir temel seçme, kimyasal Dynamics pratik hale getirme işlemini taklit edebilir.
Bu nedenle, sorunu öz, elektronik yapı sorununu çözmek için hayati öneme sahip olacak bir temel seçme.

Kullanılabilecek birçok uygun temel vardır ve sorunu sığdırmak için iyi bir seçenek vardır. Bu, hisse kuchemistry 'ın sanatı çok fazla.
Belki de en basit kümeler, Schrödinger denklemi (yani, $ \hat{H} $) için (yani, $ $), Hydrogen benzeri alar için olan (yani, $ $) çözümler içeren sdaha yüksek tür-Orbitals (STO).
Uçak-dalgalar veya gerçek zamanlı orbitler gibi diğer temel kümeler kullanılabilir ve daha fazla ayrıntı için, Helgaker tarafından standart metin [' Molesel elektronik yapı teorisine](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572) , curtik okuyucuyu başvurduk.

Yukarıdaki modelde kullanılan durumlar rastgele görünebilir, ancak hisse MACS, doğası halinde bulunan durumlara yönelik kısıtlamalar yerleştiriyor.
Özellikle, tüm geçerli elektronik hisse durumlarının, elektron etiketlerinin değişimi altında simetrik bir şekilde olması gerekir.
Diğer bir deyişle, $ \psı (x_1, x_2) $ iki elektriki 'ın Birleşik hisse durumu için dalga işlevi olsaydı $ $ \psi (x_1, x_2) =-\psi (x_2, x_1) olmalıdır.
$ $ Yasaklıyor iki elektriğini aynı hisse başında olan Pauli dışlama ilkesi, fascinettik, bu yasa doğrudan bir sonucu, aynı konum $ \psi (x_1, x_1) \mapsto \psı ( x_1, x_1) \ne-\psı (x_1, x_1) $, $ \psı (x_1, x_1) = 0 $ olmadığı.
Bu nedenle, bu durum-simetri özelliğini en uygun şekilde uygulamak için ilk durumlar seçilmelidir ve aynı durumda aynı durumda hiçbir zaman iki elektriki yoktur.
Bu, elektronik yapı için önemlidir çünkü birden çok elektrige 'ın aynı durumda olmasını yasaklıyor ve bu, ayrıca hisse maların belirli bir hisse cısındaki elektriler sayısını depolamak için tek bir hisse bitini kullanmasına izin verir.

Bu durumları ayırarak hisse bir bilgisayar üzerinde hisse kuyalarda benzetimi yapılabilir, ancak bu yaklaşım, eyaletlerini depolamak için birçok qubit gerektirdiğinden ve bir simetrik olmayan ilk durum.
Neyse ki, bu sorunlar, farklı bir perspektiften simülasyon sorununu görüntüleyerek sidestepped olabilir.