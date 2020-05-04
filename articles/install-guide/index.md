---
title: Microsoft Quantum Development Kit (QDK) yüklemeyi öğrenin
description: C#, Python ve Jupyter Notebook ortamları için Microsoft Quantum Geliştirme Seti’ni yükleme.
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: bca700660094b91f1c0dfa03f9bce1336073ca51
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680186"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum Development Kit (QDK) yükleme

Kuantum programlamaya başlayabilmek için Microsoft Quantum Development Kit (QDK) yükleme hakkında bilgi edinin. QDK aşağıdakilerden oluşur:

- Q# programlama dili
- Q# dilinde karmaşık işlevleri özetleyen bir kitaplık kümesi
- Q# ile yazılmış kuantum programlarını çalıştırmak için Python ve .NET dillerine (C#, F# ve VB.NET) yönelik API’ler
- geliştirmenizi kolaylaştıracak araçlar

Q# programları genellikle bir .NET dilinde (genellikle C#) veya Python ile yazılmış bir konak programla eşleştirilir. Bu, klasik bir programın içinden kuantum işlemlerini çağırmamıza olanak sağlar.
Ayrıca QDK, IQ# Jupyter çekirdeğine sahip Jupyter Notebook’ları için Q# desteği sağlar.

QDK, birden çok geliştirme ortamında kullanılabilir. Aşağıdaki bölümlerde tercih ettiğiniz kurulumu seçin:

- [Q# komut satırı uygulaması:](xref:microsoft.quantum.install.standalone) Q# ile komut satırından çalışmak istiyorsanız bu yaklaşımı seçin. Bunun için, aşağıdaki seçenekler gibi bir sürücü veya konak programı gerekmez.
- [Jupyter Notebook’ları için Q# yükleme:](xref:microsoft.quantum.install.jupyter) Eklenmiş metin içeren hücrelerde Q# kodu yürütmek veya kuantum bilgi işlem etkileşimli öğreticileri oluşturmak istiyorsanız bu ortamı seçin. 
- [Q# ve Python ile geliştirme:](xref:microsoft.quantum.install.python) Q# işlemlerini çağıran bir Python konak programı oluşturmak için Python ile Q#’ı birleştirmek istiyorsanız.
- [Q# ve C# veya F# ile geliştirme:](xref:microsoft.quantum.install.cs) Q# işlemlerini çağıran bir .NET konak programı oluşturmak için C# veya F# ve Q#’ı birleştirmek istiyorsanız.
