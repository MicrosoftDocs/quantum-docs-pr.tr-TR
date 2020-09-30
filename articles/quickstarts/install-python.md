---
title: Q# ve Python ile geliştirme
description: Python kullanarak Q# uygulaması oluşturmayı öğrenin.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
no-loc:
- Q#
- $$v
ms.openlocfilehash: f6a2a7d1888cfe458fa3989a27d71fcdeed0f01f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834168"
---
# <a name="develop-with-no-locq-and-python"></a>Q# ve Python ile geliştirme

Q# işlemlerini çağırmak için Python konak programları geliştirmek üzere QDK'yi yükleyin.

## <a name="install-the-qsharp-python-package"></a>`qsharp` Python paketini yükleme

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

### <a name="install-using-net-cli-and-pip-advanced"></a>[.NET CLI ve PIP kullanarak yükleme (gelişmiş)](#tab/tabid-dotnetcli)

1. Ön koşullar:

    - [Python](https://www.python.org/downloads/) 3.6 veya üzeri
    - [PIP](https://pip.pypa.io/en/stable/installing) Python paket yöneticisi
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Q# ile Python arasında birlikte çalışmayı sağlayan bir Python paketi olan `qsharp` paketini yükleyin.

    ```
    pip install qsharp
    ```

1. Jupyter ile Python tarafından kullanılan, Q# işlemlerinin derlenmesine ve çalıştırılmasına yönelik temel işlevselliği sağlayan IQ# çekirdeğini yükleyin.

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
    
***

İşte bu kadar! Artık Jupyter için hem `qsharp` Python paketine hem de IQ# çekirdeğine sahipsiniz. Bu paket Python’dan Q# işlemlerini derleyip çalıştırmak için gereken temel işlevselliği sağlar ve Q# Jupyter Not Defterlerini kullanmanıza olanak tanır.

## <a name="choose-your-ide"></a>IDE’nizi seçin

Q# dilini Python ile herhangi bir IDE'de kullanabiliyor olsanız da, Q# + Python uygulamalarınız için Visual Studio Code (VS Code) IDE kullanmanız önerilir. QDK Visual Studio Code uzantısı ile uyarılar, söz dizimi vurgulama, proje şablonları gibi daha zengin işlevlere erişim elde edersiniz.

VS Code kullanmak istiyorsanız:

- [VS Code](https://code.visualstudio.com/download)’u (Windows, Linux ve Mac) yükleyin.
- [VS Code için QDK uzantısını](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) yükleyin.

Farklı bir düzenleyici kullanmak istiyorsanız, yukarıdaki yönergelerle gerekli hazırlıkları yapabilirsiniz.

## <a name="write-your-first-no-locq-program"></a>İlk Q# programınızı yazma

Şimdi basit bir Q# programı yazıp çalıştırarak `qsharp` Python paketi yüklemenizi doğrulamaya hazırsınız.

1. `Operation.qs` adlı bir dosya oluşturup dosyaya aşağıdaki kodu ekleyerek küçük bir Q# işlemi oluşturun:

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. `Operation.qs` ile aynı klasörde, Q# `SampleQuantumRandomNumberGenerator()` işleminin simülasyonunu oluşturmak için `host.py` adlı bir Python programı oluşturun:

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    print(SampleQuantumRandomNumberGenerator.simulate())
    ```

1. Yükleme sırasında oluşturduğunuz ortamdan (yani `qsharp` yüklediğiniz Conda veya Python ortamı) şu programı çalıştırın:

    ```
    python host.py
    ```

1. Çağırdığınız işlemin sonucunu görmeniz gerekir. Bu durumda, işleminiz rastgele bir sonuç oluşturduğundan ekranda `0` veya `1` yazdırılmış olduğunu görürsünüz. Programı tekrar tekrar çalıştırırsanız her sonucu yaklaşık olarak yarı sürede görmeniz gerekir.

> [!NOTE]
> * Python kodu yalnızca normal bir Python programıdır. Python programını yazmak ve Q# işlemlerini çağırmak için Python tabanlı Jupyter Not Defterleri dahil olmak üzere herhangi bir Python ortamını kullanabilirsiniz. Python programı, Python kodunun kendisi ile aynı klasörde bulunan tüm .qs dosyalarından Q# işlemlerini içeri aktarabilir.

## <a name="next-steps"></a>Sonraki adımlar

Quantum geliştirme setini tercih ettiğiniz ortamda test ettiğinize göre, [ilk kuantum programınızı](xref:microsoft.quantum.quickstarts.qrng) yazıp çalıştırmak için bu öğreticiyi izleyebilirsiniz.
