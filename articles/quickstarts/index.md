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
ms.openlocfilehash: 3aafe78d5910027e2836f7dce72c064e75fc4436
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863705"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="84611-103">Microsoft Quantum Development Kit (QDK) yükleme</span><span class="sxs-lookup"><span data-stu-id="84611-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="84611-104">Kuantum programlamaya başlayabilmek için Microsoft Quantum Development Kit (QDK) yükleme hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="84611-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="84611-105">QDK aşağıdakilerden oluşur:</span><span class="sxs-lookup"><span data-stu-id="84611-105">The QDK consists of:</span></span>

- <span data-ttu-id="84611-106">Q# programlama dili</span><span class="sxs-lookup"><span data-stu-id="84611-106">The Q# programming language</span></span>
- <span data-ttu-id="84611-107">Q# dilindeki karmaşık işlevleri soyutlayan bir kitaplık seti</span><span class="sxs-lookup"><span data-stu-id="84611-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="84611-108">Q# dilinde yazılmış kuantum programlarını çalıştırmak için Python ve .NET dillerine (C#, F# ve VB.NET) yönelik API’ler</span><span class="sxs-lookup"><span data-stu-id="84611-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="84611-109">Geliştirmenizi kolaylaştıracak araçlar</span><span class="sxs-lookup"><span data-stu-id="84611-109">Tools to facilitate your development</span></span>

<span data-ttu-id="84611-110">Q# programları Visual Studio Code veya Visual Studio kullanarak ya da IQ# Jupyter çekirdeğine sahip Jupyter Not Defterleri aracılığıyla bağımsız uygulamalar olarak çalışabilir.</span><span class="sxs-lookup"><span data-stu-id="84611-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, or through Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>
<span data-ttu-id="84611-111">Ayrıca bir .NET dilinde (genellikle C#) veya Python’la yazılmış bir konak programla eşlenebilirler ve klasik bir programın içinden kuantum işlemleri çağırmanıza olanak verirler.</span><span class="sxs-lookup"><span data-stu-id="84611-111">They can also be paired with a host program written in a .NET language (typically C#) or Python, enabling you to call quantum operations from inside a classical program.</span></span>

<span data-ttu-id="84611-112">Bu kurulumların her birine yönelik iş akışları, [Q# programını çalıştırma yolları](xref:microsoft.quantum.guide.host-programs) konusunda açıklanmış ve karşılaştırılmıştır.</span><span class="sxs-lookup"><span data-stu-id="84611-112">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

<span data-ttu-id="84611-113">QDK'yi yüklemeye ve Q# projelerini oluşturmaya devam etmek için tercih ettiğiniz kurulumu seçin:</span><span class="sxs-lookup"><span data-stu-id="84611-113">To proceed with installing the QDK and creating Q# projects, select your preferred setup:</span></span>

<span data-ttu-id="84611-114">[Q# uygulamalarıyla geliştirme](xref:microsoft.quantum.install.standalone): Q# ile komut isteminden çalışmak için bu yaklaşımı seçin.</span><span class="sxs-lookup"><span data-stu-id="84611-114">[Develop with Q# applications](xref:microsoft.quantum.install.standalone) - Choose this approach to work with Q# from the command prompt.</span></span> <span data-ttu-id="84611-115">Bunun için, aşağıdaki seçenekler gibi bir sürücü veya konak programı gerekmez.</span><span class="sxs-lookup"><span data-stu-id="84611-115">This does not require a driver or a host program like the below options.</span></span>

<span data-ttu-id="84611-116">[Q# Jupyter Not Defterleri ile geliştirme](xref:microsoft.quantum.install.jupyter): Eklenmiş metin içeren hücrelerde Q# kodu çalıştırmak veya kuantum bilişimi etkileşimli öğreticileri oluşturmak için bu ortamı seçin.</span><span class="sxs-lookup"><span data-stu-id="84611-116">[Develop with Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) - Select this environment to run Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 

<span data-ttu-id="84611-117">[Q# ve Python ile geliştirme](xref:microsoft.quantum.install.python): Q# işlemlerini çağıran bir Python konak programı oluşturmak için Python ile Q# dilini birleştirmenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="84611-117">[Develop with Q# and Python](xref:microsoft.quantum.install.python) - Enables you to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>

<span data-ttu-id="84611-118">[Q# ve .NET ile geliştirme](xref:microsoft.quantum.install.cs): Q# işlemlerini çağıran bir .NET konak programı oluşturmak için C#, F# veya VB.NET’i Q# ile birleştirin.</span><span class="sxs-lookup"><span data-stu-id="84611-118">[Develop with Q# and .NET](xref:microsoft.quantum.install.cs) - Combine C#, F#, or VB.NET with Q# to create a .NET host program that calls Q# operations.</span></span>
