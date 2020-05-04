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
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="419c3-103">Microsoft Quantum Development Kit (QDK) yükleme</span><span class="sxs-lookup"><span data-stu-id="419c3-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="419c3-104">Kuantum programlamaya başlayabilmek için Microsoft Quantum Development Kit (QDK) yükleme hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="419c3-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="419c3-105">QDK aşağıdakilerden oluşur:</span><span class="sxs-lookup"><span data-stu-id="419c3-105">The QDK consists of:</span></span>

- <span data-ttu-id="419c3-106">Q# programlama dili</span><span class="sxs-lookup"><span data-stu-id="419c3-106">the Q# programming language</span></span>
- <span data-ttu-id="419c3-107">Q# dilinde karmaşık işlevleri özetleyen bir kitaplık kümesi</span><span class="sxs-lookup"><span data-stu-id="419c3-107">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="419c3-108">Q# ile yazılmış kuantum programlarını çalıştırmak için Python ve .NET dillerine (C#, F# ve VB.NET) yönelik API’ler</span><span class="sxs-lookup"><span data-stu-id="419c3-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="419c3-109">geliştirmenizi kolaylaştıracak araçlar</span><span class="sxs-lookup"><span data-stu-id="419c3-109">tools to facilitate your development</span></span>

<span data-ttu-id="419c3-110">Q# programları genellikle bir .NET dilinde (genellikle C#) veya Python ile yazılmış bir konak programla eşleştirilir.</span><span class="sxs-lookup"><span data-stu-id="419c3-110">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="419c3-111">Bu, klasik bir programın içinden kuantum işlemlerini çağırmamıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="419c3-111">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="419c3-112">Ayrıca QDK, IQ# Jupyter çekirdeğine sahip Jupyter Notebook’ları için Q# desteği sağlar.</span><span class="sxs-lookup"><span data-stu-id="419c3-112">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="419c3-113">QDK, birden çok geliştirme ortamında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="419c3-113">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="419c3-114">Aşağıdaki bölümlerde tercih ettiğiniz kurulumu seçin:</span><span class="sxs-lookup"><span data-stu-id="419c3-114">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="419c3-115">[Q# komut satırı uygulaması:](xref:microsoft.quantum.install.standalone) Q# ile komut satırından çalışmak istiyorsanız bu yaklaşımı seçin.</span><span class="sxs-lookup"><span data-stu-id="419c3-115">[Q# command line application:](xref:microsoft.quantum.install.standalone) choose this approach if you want to work with Q# from the command line.</span></span> <span data-ttu-id="419c3-116">Bunun için, aşağıdaki seçenekler gibi bir sürücü veya konak programı gerekmez.</span><span class="sxs-lookup"><span data-stu-id="419c3-116">This does not require a driver or a host program like the below options.</span></span>
- <span data-ttu-id="419c3-117">[Jupyter Notebook’ları için Q# yükleme:](xref:microsoft.quantum.install.jupyter) Eklenmiş metin içeren hücrelerde Q# kodu yürütmek veya kuantum bilgi işlem etkileşimli öğreticileri oluşturmak istiyorsanız bu ortamı seçin.</span><span class="sxs-lookup"><span data-stu-id="419c3-117">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 
- <span data-ttu-id="419c3-118">[Q# ve Python ile geliştirme:](xref:microsoft.quantum.install.python) Q# işlemlerini çağıran bir Python konak programı oluşturmak için Python ile Q#’ı birleştirmek istiyorsanız.</span><span class="sxs-lookup"><span data-stu-id="419c3-118">[Develop with Q# and Python:](xref:microsoft.quantum.install.python) if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="419c3-119">[Q# ve C# veya F# ile geliştirme:](xref:microsoft.quantum.install.cs) Q# işlemlerini çağıran bir .NET konak programı oluşturmak için C# veya F# ve Q#’ı birleştirmek istiyorsanız.</span><span class="sxs-lookup"><span data-stu-id="419c3-119">[Develop with Q# and C# or F#:](xref:microsoft.quantum.install.cs) if you want to combine C# or F# and Q# to create a .NET host program that calls Q# operations.</span></span>
