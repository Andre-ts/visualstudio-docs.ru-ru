---
title: Подписывание пакетов VSIX | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- signature
- signing
- authenticode
- vsix
- packages
ms.assetid: e34cfc2c-361c-44f8-9cfe-9f2be229d248
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 17179c35496fc19322c5bb951f4d04bc28e5d7bc
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80700091"
---
# <a name="signing-vsix-packages"></a>Подписывание пакетов VSIX
Сборки расширений не обязательно должны быть подписаны, прежде чем они смогут работать в Visual Studio, но это рекомендуется сделать.

 Если вы хотите защитить расширение и убедиться, что оно не было изменено, можно добавить цифровую подпись к пакету VSIX. Если VSIX подписан, установщик VSIX отобразит сообщение о том, что оно подписано, а также дополнительные сведения о самой сигнатуре. Если содержимое VSIX было изменено и VSIX еще не подписан, установщик VSIX покажет, что подпись недействительна. Установка не остановлена, но пользователь получает предупреждение.

> [!IMPORTANT]
> Начиная с Visual Studio 2015, пакеты VSIX, подписанные с помощью чего-либо, отличного от шифрования SHA256, будут идентифицированы как имеющие недопустимую подпись. Установка VSIX не заблокирована, но пользователь получит предупреждение.

## <a name="signing-a-vsix-with-vsixsigntool"></a>Подписывание VSIX с помощью Всикссигнтул
 Существует инструмент для подписи шифрования SHA256, доступный в [висуалстудиоекстенсибилити](https://www.nuget.org/profiles/VisualStudioExtensibility) на NuGet.org по адресу [всикссигнтул](https://www.nuget.org/packages/Microsoft.VSSDK.Vsixsigntool).

#### <a name="to-use-the-vsixsigntool"></a>Использование Всикссигнтул

1. Добавьте VSIX в проект.

2. Щелкните правой кнопкой мыши узел проекта в обозреватель решений, выберите **добавить &#124; Управление пакетами NuGet**.  Дополнительные сведения о NuGet и добавлении пакетов NuGet см. в разделах [Документация по NuGet](/NuGet) и [Пользовательский интерфейс диспетчера пакетов](/NuGet/Tools/Package-Manager-UI) .

3. Выполните поиск по запросу Всикссигнтул из Висуалстудиоекстенсибилити и установите пакет NuGet.

4. Теперь можно запустить Всикссигнтул из расположения локальных пакетов проекта. Сведения о сценарии подписывания (VSIXSignTool.exe/?) см. в командной строке средства.

   Например, чтобы подписать файл сертификата, защищенный паролем:

   VSIXSignTool.exeный знак/f \<certfile> /p \<password>\<VSIXfile>

## <a name="see-also"></a>См. также раздел
- [Доставка расширений Visual Studio](../extensibility/shipping-visual-studio-extensions.md)
