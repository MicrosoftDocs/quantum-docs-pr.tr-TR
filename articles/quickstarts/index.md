---
title: Microsoft Quantum Development Kit (QDK) yükleme
description: Microsoft Quantum Development Kit farklı ortamlara nasıl yüklenir?
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 378970dc911ea5a794590f8336ffc6d3f9673285
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867595"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum Development Kit (QDK) yükleme

Kuantum programlamaya başlayabilmek için Microsoft Quantum Development Kit (QDK) yükleme hakkında bilgi edinin. QDK aşağıdakilerden oluşur:

- Q# programlama dili
- Q# dilindeki karmaşık işlevleri soyutlayan bir kitaplık seti
- Q# dilinde yazılmış kuantum programlarını çalıştırmak için Python ve .NET dillerine (C#, F# ve VB.NET) yönelik API’ler
- Geliştirmenizi kolaylaştıracak araçlar

Q# programları Visual Studio Code veya Visual Studio kullanarak ya da IQ# Jupyter çekirdeğine sahip Jupyter Not Defterleri aracılığıyla bağımsız uygulamalar olarak çalışabilir.
Ayrıca bir .NET dilinde (genellikle C#) veya Python’la yazılmış bir konak programla eşlenebilirler ve klasik bir programın içinden kuantum işlemleri çağırmanıza olanak verirler.

Bu kurulumların her birine yönelik iş akışları, [Q# programını çalıştırma yolları](xref:microsoft.quantum.guide.host-programs) konusunda açıklanmış ve karşılaştırılmıştır.

QDK'yi yüklemeye ve Q# projelerini oluşturmaya devam etmek için tercih ettiğiniz kurulumu seçin:

[Q# komut satırı uygulamalarıyla geliştirme](xref:microsoft.quantum.install.standalone): Q# ile komut satırından çalışmak için bu yaklaşımı seçin. Bunun için, aşağıdaki seçenekler gibi bir sürücü veya konak programı gerekmez.

[Q# Jupyter Not Defterleri ile geliştirme](xref:microsoft.quantum.install.jupyter): Eklenmiş metin içeren hücrelerde Q# kodu çalıştırmak veya kuantum bilişimi etkileşimli öğreticileri oluşturmak için bu ortamı seçin. 

[Q# ve Python ile geliştirme](xref:microsoft.quantum.install.python): Q# işlemlerini çağıran bir Python konak programı oluşturmak için Python ile Q# dilini birleştirmenizi sağlar.

[Q# ve .NET ile geliştirme](xref:microsoft.quantum.install.cs): Q# işlemlerini çağıran bir .NET konak programı oluşturmak için C#, F# veya VB.NET’i Q# ile birleştirin.
