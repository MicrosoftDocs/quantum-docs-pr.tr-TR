---
title: Microsoft Quantum geliştirme setini (QDK) ayarlama
description: Microsoft Quantum geliştirme setini farklı ortamlar için nasıl ayarlayacağınızı öğrenin.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834491"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum geliştirme setini (QDK) ayarlama

Kuantum programlamaya başlayabilmek amacıyla, Microsoft Quantum geliştirme setini (QDK) ortamınız için nasıl ayarlayacağınızı öğrenin. QDK aşağıdakilerden oluşur:

- Q# programlama dili
- Q# dilindeki karmaşık işlevleri soyutlayan bir kitaplık seti
- Q# dilinde yazılmış kuantum programlarını çalıştırmak için Python ve .NET dillerine (C#, F# ve VB.NET) yönelik API’ler
- Geliştirmenizi kolaylaştıracak araçlar

Q# programları Visual Studio Code veya Visual Studio kullanarak, IQ# Jupyter çekirdeğine sahip Jupyter Not Defterleri aracılığıyla ya da Python veya .NET dilinde (C#, F#) yazılmış bir konak ortamıyla eşlenmiş bağımsız uygulamalar olarak çalışabilir. Q# programlarını [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) veya [Docker](#use-the-qdk-with-docker) kullanarak da çevrimiçi olarak çalıştırabilirsiniz. 

## <a name="options-for-setting-up-the-qdk"></a>QDK’yı ayarlama seçenekleri

QDK’yı üç şekilde kullanabilirsiniz:

- [QDK’yı yerel olarak yükleyerek](#install-the-qdk-locally)
- [QDK’yı çevrimiçi olarak kullanarak](#use-the-qdk-online)
- [QDK Docker görüntüsü kullanarak](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a>QDK’yı yerel olarak yükleme

Q# kodunu sık kullandığınız IDE’lerin çoğunda geliştirebilir, aynı zamanda Q# ile Python ve .NET (C#, F#) gibi diğer dilleri tümleştirebilirsiniz.

|&nbsp; | **VS Code<br>(2019 veya üzeri)**| **Visual Studio<br>(2019 veya üzeri)** | **Jupyter Notebooks** | **Komut satırı**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|**İşletim sistemi** |Windows, macOS, Linux |Yalnızca Windows |Windows, macOS, Linux |Windows, macOS, Linux |
|<br>**Q# tek başına** |<br>[Yükleme](xref:microsoft.quantum.install.standalone) |<br> [Yükleme](xref:microsoft.quantum.install.standalone)  |<br> [Yükleme](xref:microsoft.quantum.install.jupyter) |<br>[Yükleme](xref:microsoft.quantum.install.standalone)|
|**Q# ve Python** |[Yükleme](xref:microsoft.quantum.install.python) |[Yükleme](xref:microsoft.quantum.install.python) |[Yükleme](xref:microsoft.quantum.install.jupyter) |[Yükleme](xref:microsoft.quantum.install.python) |
|**Q# ve .NET (C#, F#)**|[Yükleme](xref:microsoft.quantum.install.cs) |[Yükleme](xref:microsoft.quantum.install.cs)|&#10006; |[Yükleme](xref:microsoft.quantum.install.cs) |

## <a name="use-the-qdk-online"></a>QDK’yı çevrimiçi olarak kullanma

Şu seçenekler sayesinde, yerel olarak herhangi bir program yüklemeden Q# kodu geliştirebilirsiniz:

|Kaynak|Avantajlar|Sınırlamalar|
|---|---|---|
|[**Visual Studio Codespaces**](xref:microsoft.quantum.install.standalone)|Zengin bir çevrimiçi geliştirme ortamı  |Bir Azure aboneliği ve planı gerekir |
|[**Binder**](xref:microsoft.quantum.install.binder) | Ücretsiz, çevrimiçi not defteri deneyimi |Kalıcılık yok |

## <a name="use-the-qdk-with-docker"></a>QDK’yı Docker ile kullanma

QDK Docker görüntümüzü yerel Docker yüklemenizde veya ACI gibi, Docker görüntülerini destekleyen herhangi bir hizmet aracılığıyla bulutta kullanabilirsiniz.

IQ# Docker görüntüsünü https://github.com/microsoft/iqsharp/#using-iq-as-a-container sayfasından indirebilirsiniz. 

Geliştirme ortamlarını hızla tanımlamak için Docker’ı bir Visual Studio Code Uzaktan Geliştirme Kapsayıcısı ile de kullanabilirsiniz. VS Code Geliştirme Kapsayıcıları hakkında daha fazla bilgi için bkz. https://github.com/microsoft/Quantum/tree/master/.devcontainer.

## <a name="next-steps"></a>Sonraki adımlar

Bu kurulumların her birine yönelik iş akışları, [Q# programını çalıştırma yolları](xref:microsoft.quantum.guide.host-programs) konusunda açıklanmış ve karşılaştırılmıştır.
