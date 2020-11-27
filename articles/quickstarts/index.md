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
ms.openlocfilehash: c6e128ea8b3845336fb692d2bceefda998b935d9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228857"
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

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><b>VS Code<br>(2019 veya üzeri)</b></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="Visual Studio" width="50"/><br><b>Visual Studio<br>(2019 veya üzeri)</b></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><b>Jupyter Notebooks</b></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><b>Komut satırı</b></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><b>İşletim sistemi desteği:</b></td>
        <td align="center">Windows, macOS, Linux</td>
        <td align="center">Yalnızca Windows</td>
        <td align="center">Windows, macOS, Linux</td>
        <td align="center">Windows, macOS, Linux</td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><b>Q# tek başına</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Yükleme</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Yükleme</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.jupyter">Yükleme</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Yükleme</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><b>Q# ve Python</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Yükleme</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Yükleme</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Yükleme</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Yükleme</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><b>Q# ve .NET (C#, F#)</b></td> 
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Yükleme</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Yükleme</a></td>
        <td align="center">&#10006;</td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Yükleme</a></td>
   </tr>
</table>

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
