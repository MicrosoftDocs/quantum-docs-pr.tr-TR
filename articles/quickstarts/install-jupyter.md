---
title: Q# Jupyter Not Defterleri ile geliştirme
description: Jupyter Not Defterleri kullanarak Q# uygulaması oluşturmayı öğrenin.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.jupyter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4cef9b7252a2199b2ea995c4cf819a3582d9ca8f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844287"
---
# <a name="develop-with-no-locq-jupyter-notebooks"></a>Q# Jupyter Not Defterleri ile geliştirme

Q# Jupyter Not Defterlerinde Q# işlemleri geliştirmek için QDK'yi yükleyin.

Jupyter Not Defterleri yönergeler, notlar ve diğer içeriklerin yanı sıra yerinde kod çalıştırmaya olanak sağlar. Bu ortam, ekli açıklamalar veya kuantum bilişimi etkileşimli öğreticileri ile Q# kodu yazmak için idealdir. Kendi Q# not defterlerinizi oluşturmaya başlamak için gerekenler aşağıda verilmiştir.

## <a name="install-the-ino-locq-jupyter-kernel"></a>IQ# Jupyter çekirdeğini yükleme

IQ# (ay-kü-şarp olarak okunur) öncelikli olarak Jupyter ve Python tarafından .NET Core SDK için kullanılan ve Q# işlemlerinin derlenmesine ve simülasyonunun yapılmasına yönelik temel işlevselliği sağlayan bir uzantıdır.

### <a name="install-using-conda-recommended"></a>[Conda kullanarak yükleme (önerilir)](#tab/tabid-conda)

1. [Miniconda](https://docs.conda.io/en/latest/miniconda.html) veya [Anaconda](https://www.anaconda.com/products/individual#Downloads)'yı yükleyin. **Not:** 64 bit yüklemesi gerekir.

1. Anaconda İstemini açın.

   - Ya da PowerShell veya pwsh kullanmayı tercih ediyorsanız: Bir kabuğu açın, `conda init powershell` komutunu çalıştırın, ardından kabuğu kapatıp yeniden açın.

1. Şu komutları çalıştırarak gerekli paketlerle (Jupyter Notebook ve IQ# dahil) `qsharp-env` adlı yeni bir Conda ortamı oluşturup etkinleştirin:

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. Yüklemenizi doğrulamak için aynı terminalden `python -c "import qsharp"` komutunu çalıştırın ve yerel paket önbelleğinizi tüm gerekli QDK bileşenleriyle doldurun.

### <a name="install-using-net-cli-advanced"></a>[.NET CLI kullanarak yükleme (gelişmiş)](#tab/tabid-dotnetcli)

1. Ön koşullar:

    - [Python](https://www.python.org/downloads/) 3.6 veya üzeri
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. `Microsoft.Quantum.IQSharp` paketini yükleyin.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

> [!NOTE]
> `dotnet iqsharp install` adımında bir hata alırsanız yeni bir terminal penceresi açın ve yeniden deneyin.
> Bu adım da işe yaramazsa yüklü olan `dotnet-iqsharp` aracını (Windows’da `dotnet-iqsharp.exe`) bulup çalıştırmayı deneyin:
> ```
> /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
> ```
> `/path/to/dotnet-iqsharp`, dosya sisteminizdeki `dotnet-iqsharp` aracının mutlak yolu ile değiştirilmelidir.
> Genellikle bu, kullanıcı profili klasörünüzdeki `.dotnet/tools` altında bulunur.
    
**_

İşte bu kadar! Artık Jupyter için IQ# çekirdeğine sahipsiniz. Bu çekirdek Q# Jupyter Not Defterlerinden Q# işlemlerini derlemek ve çalıştırmak için gereken temel işlevselliği sağlar.

## <a name="create-your-first-no-locq-notebook"></a>İlk Q# not defterinizi oluşturma

Artık basit bir Q# işlemi yazıp çalıştırarak Q# Jupyter Notebook yüklemenizi doğrulamaya hazırsınız.

1. Yükleme sırasında oluşturduğunuz ortamdan (yani oluşturduğunuz Conda ortamı veya Jupyter’ı yüklediğiniz Python ortamı) Jupyter Notebook sunucusunu başlatmak için şu komutu çalıştırın:

    ```
    jupyter notebook
    ```

    - Jupyter Notebook otomatik olarak tarayıcınızda açılmazsa komut satırı tarafından sağlanan URL’yi kopyalayıp tarayıcınıza yapıştırın.

1. Çekirdekle bir Jupyter Notebook oluşturmak için _ *New Q# →** öğesini seçin Q# ve ilk not defteri hücresine aşağıdaki kodu ekleyin:

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. Not defterinin şu hücresini çalıştırın:

    ![Q# kodu içeren Jupyter Notebook hücresi](~/media/install-guide-jupyter.png)

    Hücrenin çıktısında `SampleQuantumRandomNumberGenerator` görmeniz gerekir. Jupyter Notebook’ta çalışırken Q# kodu derlenir ve hücre, bulduğu tüm işlemlerin adlarını çıktı olarak verir.

1. Yeni bir hücrede, az önce oluşturduğunuz işlemi `%simulate` komutunu kullanarak (simülatör içinde) çalıştırın:

    ![%simulate magic içeren Jupyter Not Defteri hücresi](~/media/install-guide-jupyter-simulate.png)

    Çağırdığınız işlemin sonucunu görmeniz gerekir. Bu durumda, işleminiz rastgele bir sonuç oluşturduğundan ekranda `Zero` veya `One` yazdırılmış olduğunu görürsünüz. Hücreyi tekrar tekrar çalıştırırsanız her sonucu yaklaşık olarak yarı sürede görmeniz gerekir.

## <a name="next-steps"></a>Sonraki adımlar

Artık Q# Jupyter Not Defterleri için QDK’yi yüklediğinize göre, Q# kodunu doğrudan Jupyter Notebook ortamı içinde yazarak [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırabilirsiniz.

Q# Jupyter Not Defterleri ile yapabileceklerinize ilişkin daha fazla örnek için lütfen şuraya göz atın:

- [Q# ve Jupyter Notebook’a giriş](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Burada, Jupyter ortamında Q# kullanmayla ilgili daha fazla ayrıntı sağlayan bir Q# Jupyter Not Defteri bulacaksınız.
- [Quantum Kataları](xref:microsoft.quantum.overview.katas), kendi hızınızda ilerleyebileceğiniz öğreticilerden ve Q# Jupyter Not Defterleri biçimindeki programlama alıştırması setlerinden oluşan bir açık kaynak koleksiyondur. [Quantum Katas öğretici not defterleri](https://github.com/microsoft/QuantumKatas#tutorial-topics) iyi bir başlangıç noktasıdır. Quantum Kataları, size aynı anda hem kuantum bilişiminin hem de Q# programlamanın öğelerini öğretmeyi amaçlar. Bu öğreticiler, Q# Jupyter Not Defterleri ile oluşturabileceğiniz içerik türüne dair harika bir örnektir.
