---
title: Hisse dinamikleri | Microsoft Docs
description: Hisse Dynamics kavramsal belgeleri
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantumdynamics
ms.openlocfilehash: 0fd27e59921fdf8429bf164c4c64cfa3b8e44160
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185350"
---
# <a name="quantum-dynamics"></a>Hisse dinamikleri

Hisse vavaların bir ilk hisse durumu $ \ket{\psı (0)} [$ ' ın](xref:microsoft.quantum.concepts.dirac) zamana göre nasıl değiştiğini anlamak için, hisse adetikleri büyük ölçüde bir adetdir.
Özellikle, bu ilk koşul için bir hisse ma durumu, bir evlenme süresi ve hisse dili olan hisse kullanımı sisteminin bir belirtimi verildiğinde, bir hisse durumu $ \ket{\psı (t)} $,.
Hisse ve Dynamics 'i açıklamaya geçmeden önce, bir adım adım geri dönüp klasik Dynamics 'i düşünmek yararlı olur. bu sayede, hisse yaraların klasik Dynamics 'ten farklı olan gerçek olmayan konularda Öngörüler sağladığından öngörülere göz atın.

Klasik Dynamics 'te bir parçacığın konumunun $F (x, t) = ma = m\frac {\ gg ^ 2} {\dd t ^ 2} {x} (t) $ ' e (x, t) $, $m $ $F ' in kütle ve $a $ ' in hızlandırılıdır.
Ardından, bir ilk konum $x (0) $, evlenme saati $t $ ve parçacık üzerinde işlem yapan güçlerin açıklaması verildiğinde, $x (t) $ için Newton 'in denklemleri tarafından verilen fark denklemini çözerek $x (t) $ bulabilirsiniz.
Güçleri bu şekilde belirtmek sorunun biraz bir yoludur.
Bu nedenle, her zaman sistemin olası enerjisi açısından, ABD $-\partial_x V (x, t) = d \frac{\gg ^ 2} {\dd t ^ 2} {x} (t) $ ' i sağlayan potansiyel enerji koşullarına göre geliştirdik.
Bu nedenle, bir parçacık için sistemin dinamiki yalnızca olası enerji işlevi, parçacık kütle ve evrimsel süre tarafından belirtilir.

Daha geniş bir dil genellikle $F = Ma $ ' dan fazla olan klasik Dynamics için sunulmuştur.
Daha önce hisse kutları açısından yararlı olan bir formül, Hamiltonian mekanizması.
Hamiltonian mekanizması içinde, bir sistem ve (Genelleştirilmiş) konumların toplam enerjisi ve momenta, rastgele bir klasik nesnenin hareketini anlatmak için gereken tüm bilgileri verir.
Özellikle, $f (x, p, t) $ öğesinin Genelleştirilmiş konumların bazı işlevleri $x $ ve momenta $p $ olmasına izin verebilir ve $H (x, p, t) $ 'nin Hamiltonian işlevi olmasına izin verin.
Örneğin, $f (x, p, t) = x (t) $ ve $H (x, p, t) = p ^ 2 (t)/2m-V (x, t) $ olursa, Newtonian Dynamics 'in yukarıdaki durumunu kurtarırız.
Bu durumda, \begin{hizalaması} \frac{d}{DT} f & = \partial_t f-(\partial_x H\partial_p f + \partial_p H\partial_x f)\\\\ & \defeq \partial_t f + \\{f, H\\}.
\end{hizalaması} burada $\\{f, H\\} $, [Pofer ayracı](https://en.wikipedia.org/wiki/Poisson_bracket) olarak adlandırılır ve bir klasik rol nedeniyle, Dynamics 'in tanımlanmakta olduğu merkezi rol nedeniyle klasik olarak görünür.

Hisse dinamikleri, tam olarak aynı dil kullanılarak açıklanabilir.
Hamiltonian veya toplam enerji, tamamen kapatılan bir hisse sisteminin dinamiki olduğunu belirtir.
Bununla birlikte, iki ikisi arasında bazı önemli farklılıklar vardır.
Klasik bir $x $ ve $p $ yalnızca sayılardan oluşmalıdır, bu da hisse anlardır.
Gerçekten de bu kişiler bile $xp \ne px $.

Bu işlem dışı nesneleri açıklayan sağ matematik kavramı, $x $ ve $p $ ' ın yalnızca bir matris kavramıyla saatle çakışan bir dizi değer kümesi albildiği durumlarda bir işleçtir.
Bu nedenle, kolaylık sağlaması için hisse sistemimizin, [vektör ve matrisler](xref:microsoft.quantum.concepts.vectors)kullanılarak açıklanabilmesi için sonlu olduğunu varsayacağız.
Daha da bu Matrislerin hermitian olması gerekir (matrisin eşleniği devrik orijinal matrile aynı olduğu anlamına gelir).
Bu, matrislerin eigendeğerlerinin gerçek değerli olmasını güvence altına alır; bir sanal numarayı geri alma yaptığımız konum gibi bir miktarı ölçyoruz olduğundan emin olmak için belirlediğimiz bir koşul.

Hisse macılarındaki konum ve itici güç 'nin işleçlere göre değişmesi gerektiğinde, Hamiltonian işlevinin benzer şekilde bir işleçle değiştirilmeleri gerekir.
Örneğin, boş alandaki bir parçacık için $H (x, p) = p ^ 2/2m $ iken, hisse MACS 'nin $ \hat{H} $, $ \hat{H} = \hat{p} ^ 2/2m $, burada $ \hat{p} $, itici güç işlecinin olduğu Hamiltonian işleci.
Bu perspektiften itibaren, klasik 'dan hisse ya da yalnızca işleçlere sahip normal Dynamics 'te kullanılan değişkenlerin yerini değiştirmeyi içerir.
Sıradan klasik Hamiltonian 'yi hisse dilinde çevirerek Hamiltonian işlecini oluşturduktan sonra, bir rastgele hisse mekanik miktarı (örn. hisse mekanik operatör) $ \hat{f} (t) $ değerini \begin{ile ifade edebiliriz align} \frac{d}{DT} \hat{f} = \partial_t \hat{f} + [\hat{f}, \hat{H}], \end{hizalaması}; burada $ [f, H] = fH-HF $, Commutator olarak bilinir.
Bu ifade, yukarıda verilen klasik ifadeye benzer şekilde, $f $ ile $H $ arasında Commutator ile değiştirilen Pofer $\\{f, H\\} $ arasındaki fark ile değiştirilmiştir.
Bu, klasik bir Hamiltonian alma ve bunu bir hisse Hamilton bulmak için kullanma süreci, standart bir ölçü olarak on hisse

En çok hangi işleçleri $f $ ilgilentik?  Bunun yanıtı çözmek istediğimiz soruna bağlıdır.
Bulmanın en faydalı miktarı, Dynamics hakkında öğrendiğimiz her şeyi ayıklamak için daha önceki kavramsal belgelerde ele alındığı gibi hisse maç işleçtir.
Bunu yaptıktan sonra (ve bunun saf bir duruma sahip olduğu durum için sonucu basitleştirerek), hisse Schrödinger denklemi, \begin{hizalaması} ı\partial_t \ket{\psı (t)} = \hat{H} (t) \ket{\psı (t)} bulunur.
\end{hizalaması}

Bu denklem, yukarıda verilen sayıdan daha az sezgisel olsa da, hisse veya klasik bir bilgisayarda hisse veya Klasik bilgisayar üzerinde hisse nasıl benzediğini anlamak için belki de en basit ifade verir.
Bunun nedeni, fark denklemi çözümünün şu biçimde ifade edilmesi ($t $) \begin{hizalaması} \ket{\psı (t)} = e ^ {-iHt} \ket{\psı (0)}.
\end{hizalaması} burada $e ^ {-iHt} $ bir Unitary matrisi.
Yani, her türlü Unitary matrisini yakından tahmin ettiğinden, bunu gerçekleştirmek için tasarlanabileceğinden bir hisse uygun hale getirebileceği anlamına gelir.
Bu işlem, hisse maç süresini uygulamak için bir hisse devresini bulma işlemi ile $e ^ {-iht} $, genellikle hisse simülasyonu veya belirli bir dinamik hisse simülasyonu olarak adlandırılır.
