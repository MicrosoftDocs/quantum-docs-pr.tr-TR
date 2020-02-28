---
title: Hisse bilgi işlem sözlüğü
description: Hisse bilgi işlem için kullanılan ortak terimler, eylem ve nesnelerin bir sözlüğü.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: f47d87f5bc9d677baa12a7ac1581af72894e8a4b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909900"
---
# <a name="quantum-computing-glossary"></a>Hisse bilgi işlem sözlüğü

|Süre|Tanım|
|-------------|----------|
|Adjoint|İşlemin karmaşık eşleniği devrik. Bir Unitary işleci uygulayan işlemler için, adjoint işlemin tersidir.|
|Çağrılabilir|İşlemler ve işlevler toplu olarak *callables*olarak bilinir.|
|Standart|Ön halde tanımlanan mantık üzerinde Q # oluşturulurken tanımlanan işlemler ve işlevler. Standart kitaplık uygulamasının hedef makinelere göre belirsiz olması.|
|Clienfford grubu|Bloch Sphere 'ın ocklerini kaplayan işlem kümesi. Bunlar şunlardır: `X`, `Y`, `Z`, `H` ve `S`|
|Tarafından|Hedef işlem için bir veya daha fazla qubit, etkinleştiriciler olarak alan bir hisse.|
|Dirac gösterimi|Hisse durumunun toplu gösterimi. Daha fazla bilgi için bkz. [Dirac gösterimi](xref:microsoft.quantum.concepts.dirac) bölümü.|
|Eigenvalues ve Eigenvektör'ler|Ayrıntılar için [Gelişmiş matris bölümüne](xref:microsoft.quantum.concepts.matrix-advanced) bakın.|
|EPR çifti|[Çan durumu](https://en.wikipedia.org/wiki/Bell_state) olarak da bilinen|
|Ri|Durum zaman içinde nasıl değişir. Bir örnek için <xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials> bölümüne bakın. |
|İşlev|Q # dilinde yalnızca klasik yordamlar|
| <a id="global-phase"></a>Küresel aşama | ^ {İ\phi} $ $e karmaşık bir sayının bir katı kadar özdeş olan iki durum, küresel bir aşamaya göre farklılık gösterir. Yerel aşamaların aksine, genel aşamalar herhangi bir ölçümle gözlemlenemez. Daha fazla ayrıntı için bkz. [Pauli ölçümleri](xref:microsoft.quantum.concepts.pauli) . |
|Ölçüm|Bir qubitden (veya qubits kümesinden) klasik bir bit elde edin. Daha fazla bilgi için [qubit kavramları](xref:microsoft.quantum.concepts.qubit) bölümüne bakın.|
|Değiştirilebilir|Değeri oluşturulduktan sonra değiştirilmiş olan bir değişken.|
|Ad Alanı|İlgili adların toplanması için bir etiket (genellikle işlemler, işlevler ve türler). Örneğin ad alanı [`Microsoft.Quantum.Preparation`](xref:microsoft.quantum.preparation) , ilk durumları hazırlamaya yardımcı olan standart kitaplıkta tanımlanan tüm sembolleri Etiketler.|
|İşlem|Q # içinde temel hisse yürütme birimi. Bu kabaca C, C++ veya Python'da işlevle ya da C# veya Java'da statik yöntemle eşdeğerdir.|
|İşleç uygulaması|Hisse bir işlem gerçekleştiriliyor. Bu, genellikle geçerli durum vektörüne bir Unitary matrisi uygular. Daha fazla ayrıntı için bkz. [hisse ve tanıtım kavramlarına giriş](xref:microsoft.quantum.concepts.intro) .|
|Oracle|Çalışma zamanında bir hisse algoritmasına veri bağımlı bilgiler sağlayan bir altyordam. Genellikle amaç, üst konumdaki girişlere karşılık gelen çıkışların üst konumunu sağlamaktır.   |
|Kısmi uygulama|Tüm gerekli parametreler olmadan bir işlev veya işlem çağrılıyor. , Yalnızca gelecekteki bir uygulama sırasında sağlanan eksik parametrelere ihtiyacı olan yeni bir çağrılabilir döndürür.|
|Pauli Işleçleri|`X`, `Y` ve `Z` hisse kapıları.|
|Prelude dili|Q # düzeyi yerine her bir hedef makine tarafından tanımlanan temel ve klasik işlemler ve işlevler kümesi.|
|Hisse devresi|Bir hisse bilgisayar için programın temsili. Daha fazla bilgi için <xref:microsoft.quantum.concepts.circuits> bölümüne bakın.|
|Hisse durumu|Sistemdeki qubits temsili. Bu, genellikle karmaşık bir sütun vektörü olarak gösterilir. Daha fazla bilgi için bkz. <xref:microsoft.quantum.concepts.vectors>. |
|Qubit|Hisse birimi depolama birimi. Daha fazla bilgi için <xref:microsoft.quantum.concepts.qubit> bölümüne bakın.|
|Yineleme-Until-başarılı|Bilsel olarak başarılı olan bir hisse algoritması. Hata sonrasında, yordam başarılı olana kadar yeniden denenecek (veya sınıra ulaşılmıştır). |
|Hedef makine|Soyut bir hisse programını donanım veya benzetim doğrultusunda alçalt bir derleme hedefi. Bu genellikle, geçit değiştirme, hata düzeltme için kodlama, geometrik düzen ve diğerleri gibi birçok amaç için yeniden yazma işlemlerini içerir.|
|Le|Virgülle ayrılmış türler parantez ile birlikte gruplandırılır. |
|Kullanıcı tanımlı tür|Tek bir birim olarak başvurulabilen yerleşik veya önceden tanımlanmış türlerin koleksiyonu.|

