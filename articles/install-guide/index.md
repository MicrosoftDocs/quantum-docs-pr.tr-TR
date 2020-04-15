---
title: Microsoft Quantum Development Kit (QDK) yüklemeyi öğrenin
description: C#, Python ve Jupyter Notebook ortamları için Microsoft Quantum Geliştirme Seti’ni yükleme.
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 5fafb736f34d27f9233370a0a8a66c0613606048
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/13/2020
ms.locfileid: "77904783"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="2fc4d-103">Microsoft Quantum Development Kit (QDK) yükleme</span><span class="sxs-lookup"><span data-stu-id="2fc4d-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="2fc4d-104">Kuantum programlamaya başlayabilmek için Microsoft Quantum Development Kit (QDK) yükleme hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="2fc4d-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="2fc4d-105">QDK aşağıdakilerden oluşur:</span><span class="sxs-lookup"><span data-stu-id="2fc4d-105">The QDK consists of:</span></span>

- <span data-ttu-id="2fc4d-106">Q# programlama dili</span><span class="sxs-lookup"><span data-stu-id="2fc4d-106">the Q# programming language</span></span>
- <span data-ttu-id="2fc4d-107">Q# dilinde karmaşık işlevleri özetleyen bir kitaplık kümesi</span><span class="sxs-lookup"><span data-stu-id="2fc4d-107">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="2fc4d-108">Q# ile yazılmış kuantum programlarını çalıştırmak için Python ve .NET dillerine (C#, F# ve VB.NET) yönelik API’ler</span><span class="sxs-lookup"><span data-stu-id="2fc4d-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="2fc4d-109">geliştirmenizi kolaylaştıracak araçlar</span><span class="sxs-lookup"><span data-stu-id="2fc4d-109">tools to facilitate your development</span></span>

<span data-ttu-id="2fc4d-110">Q# programları genellikle bir .NET dilinde (genellikle C#) veya Python ile yazılmış bir konak programla eşleştirilir.</span><span class="sxs-lookup"><span data-stu-id="2fc4d-110">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="2fc4d-111">Bu, klasik bir programın içinden kuantum işlemlerini çağırmamıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="2fc4d-111">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="2fc4d-112">Ayrıca QDK, IQ# Jupyter çekirdeğine sahip Jupyter Notebook’ları için Q# desteği sağlar.</span><span class="sxs-lookup"><span data-stu-id="2fc4d-112">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="2fc4d-113">QDK, birden çok geliştirme ortamında kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="2fc4d-113">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="2fc4d-114">Aşağıdaki bölümlerde tercih ettiğiniz kurulumu seçin:</span><span class="sxs-lookup"><span data-stu-id="2fc4d-114">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="2fc4d-115">[C# için Q# yükleme:](xref:microsoft.quantum.install.cs) Q# işlemlerini çağıran bir C# konak programı oluşturmak için C# ile Q#’ı birleştirmek istiyorsanız bu ortamı seçin.</span><span class="sxs-lookup"><span data-stu-id="2fc4d-115">[Install Q# for C#:](xref:microsoft.quantum.install.cs) choose this environment if you want to combine C# and Q# to create a C# host program that calls Q# operations.</span></span>
- <span data-ttu-id="2fc4d-116">[Python için Q# yükleme:](xref:microsoft.quantum.install.python) Q# işlemlerini çağıran bir Python konak programı oluşturmak için Python ile Q#’ı birleştirmek istiyorsanız bu ortamı seçin.</span><span class="sxs-lookup"><span data-stu-id="2fc4d-116">[Install Q# for Python:](xref:microsoft.quantum.install.python) choose this environment if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="2fc4d-117">[Jupyter Notebook’ları için Q# yükleme:](xref:microsoft.quantum.install.jupyter) Eklenmiş metin içeren hücrelerde Q# kodu yürütmek veya kuantum bilgi işlem etkileşimli öğreticileri oluşturmak istiyorsanız bu ortamı seçin.</span><span class="sxs-lookup"><span data-stu-id="2fc4d-117">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> <span data-ttu-id="2fc4d-118">Q#’ı harici bir klasik konak programıyla birleştirmek istiyorsanız bu ortamı seçmeyin.</span><span class="sxs-lookup"><span data-stu-id="2fc4d-118">Do not choose this environment if you want to combine Q# with an external classical host program.</span></span>
