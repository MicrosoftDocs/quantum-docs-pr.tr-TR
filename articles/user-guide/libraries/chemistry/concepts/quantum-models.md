---
title: Elektronik sistemler için hisse modelleri
description: Molesel elektronik sistemlerinin hisse modellemesi kullanarak nasıl benzetilen olduğunu öğrenin.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.quantummodels
no-loc:
- Q#
- $$v
ms.openlocfilehash: c12ab277f06bed61991a26af96953ccdbf72b642
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856213"
---
# <a name="quantum-models-for-electronic-systems"></a>Elektronik sistemler için hisse modelleri

Elektronik sistemlerin benzetimini yapmak için önce, yukarıda açıklanan kurallı bir işlem yordamıyla bulunabilir Hamiltonian 'yi belirterek başladık.
Özellikle, $N _e $ elektriler için momenta $p _i $ (üç boyutta) ve toplu $m _E $ ve konum vektörlerini $x _i Hamiltonian işleci, \begin{Equation} \hat{H} = \sum \_ {ı = 1} ^ {N \_ e} \frac{\hat{p} \_ i ^ 2} {2m \_ e} + \frac {1} {2} \ Sum \_ {i\ne j okur} \frac{e ^ 2} {| \hat{x} \_ i-\hat{x} \_ j |}-\Sum \_ {i, k} \frac{z \_ ke ^ 2} {| \hat{x} \_ i-{y} \_ k |} + \frac {1} {2} \ sum_ {k\ne k '} \frac{Z \_ KZ \_ {k '} e ^ 2} {| y \_ k-y \_ k ' |}. \label{EQ: ham} \end{Equation} momenta işleçleri $ \hat{p} \_ i ^ 2 $, gerçek alanda Laplacıa işleçleri olarak görüntülenebilir, yani $ \hat{p} \_ i ^ 2 =-\partial \_ {x \_ i} ^ 2-\ partial {y i} ^ \_ \_ 2-\ partial \_ {z \_ i} ^ 2 $.
Burada, nucleı 'nin moleule için geri kalanı olduğunu basitleştirecek şekilde yaptık.
Bu, Born-Oppenheimer yaklaşık olarak bilinir ve, elektron kütle yaklaşık $1/1836 $ prototipn 'ın kütle olduğundan, $ \hat{H} $ düşük enerji enerji yelpazesi için geçerli olduğunu eğilimindedir.
Bu Hamiltonian işleci, $N \_ e $ elektriler sistemi için enerji yazarak ve [hisse](xref:microsoft.quantum.chemistry.concepts.quantumdynamics)malarca açıklanan kurallı ölçü sürecini uygulayarak kolayca bulunabilir.

$E ^ {-i\hat {H} t} $ için Unitary matris gösterimini oluşturmak için, matris olarak $ \hat{H} $ işlecini temsil etmemiz gerekir.
Bunun için, içindeki sorunu temsil eden bir koordinat sistemi veya temeli seçmemiz gerekir.
Örneğin, $ \ psi_j $, $N _e $ elektriler için dikey bir temel işlevler kümesi ise matrisi tanımlayabiliriz

\begin{Equation} H \_ {i, j} = \int \_ {-\infty} ^ \infty\ınt \_ {-\infty} ^ \infty \psı ^ { \* } \_ ı (x \_ 1) \hat{H} \psı \_ j (x \_ 2) \gg ^ 3x \_ 1 \dd ^ 3x \_ 2. \ Label {EQ: discreteHam} \end{Equation}

Prensibi, $ \hat{H} $ işlecinin sınırsız olduğu ve sonlu bir boyut alanı üzerinde davranmadığından, \_ \{ yukarıda $H i, j $ olan öğe olan matris \} .
Bu, bir taban kümesinin çok küçük olarak seçilmesinde hataların tahakkuk etmesidir. Ancak, büyük bir temel seçme, kimyasal Dynamics pratik hale getirme işlemini taklit edebilir.
Bu nedenle, sorunu öz, elektronik yapı sorununu çözmek için hayati öneme sahip olacak bir temel seçme.

Kullanılabilecek birçok uygun temel vardır ve sorunu sığdırmak için iyi bir seçenek vardır. Bu, hisse kuchemistry 'ın sanatı çok fazla.
Belki de en basit kümeler, Schrödinger denklemi (yani, $ \hat{H} $) için (yani, $ $), Hydrogen benzeri alar için olan (yani, $ $) çözümler içeren sdaha yüksek tür-Orbitals (STO).
Uçak-dalgalar veya gerçek zamanlı orbitler gibi diğer temel kümeler kullanılabilir ve daha fazla ayrıntı için, Helgaker tarafından standart metin [' Molesel Electronic-Structure teorisi '](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572) ' ne değerli okuyucuya başvurduk.

Yukarıdaki modelde kullanılan durumlar rastgele görünebilir, ancak hisse MACS, doğası halinde bulunan durumlara yönelik kısıtlamalar yerleştiriyor.
Özellikle, tüm geçerli elektronik hisse durumlarının, elektron etiketlerinin değişimi altında simetrik bir şekilde olması gerekir.
Diğer bir deyişle, $ \psı (x_1, x_2) $ iki elektriki 'ın Birleşik hisse MAI durumunun dalga işlevidir, bundan sonra $ $ \psi (x_1, x_2) =-\psi (x_2, x_1) olmalıdır.
$ $ Yasaklıyor iki elektriki, her zaman aynı hisse Vada olan Pauli dışlama ilkesi, fascinattik, bu yasaların doğrudan bir sonucu, aynı konumun $ \psi (x_1, x_1) \mapsto \psi (x_1, x_1) \ne-\psı (x_1, x_1) $ değerinden $ \psı (x_1 , x_1) = 0 $.
Bu nedenle, bu durum-simetri özelliğini en uygun şekilde uygulamak için ilk durumlar seçilmelidir ve aynı durumda aynı durumda hiçbir zaman iki elektriki yoktur.
Bu, elektronik yapı için önemlidir çünkü birden çok elektrige 'ın aynı durumda olmasını yasaklıyor ve bu, ayrıca hisse maların belirli bir hisse cısındaki elektriler sayısını depolamak için tek bir hisse bitini kullanmasına izin verir.

Hisse matları bu durumları ayırarak bir hisse bilgisayar üzerinde simülabildiğinden, bu yaklaşım, durumları depolamak için birçok qubit gerektirdiğinden ve simetrik olmayan bir ilk durumu hazırlamak için karmaşık bir durum hazırlama yordamına ihtiyaç duyduğundan bu yaklaşımda sahiptir.
Neyse ki, bu sorunlar, farklı bir perspektiften simülasyon sorununu görüntüleyerek sidestepped olabilir.
