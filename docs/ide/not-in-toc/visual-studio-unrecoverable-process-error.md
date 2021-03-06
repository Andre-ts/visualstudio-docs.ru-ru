---
title: Процесс обнаружил неустранимую ошибку
ms.date: 09/10/2020
ms.topic: troubleshooting
helpviewer_keywords:
- unrecoverable error
- error, process
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e1c9dc5053e2168482f4463f805bdc5e724ef6b0
ms.sourcegitcommit: d9dd86c421532cfca6c0c5761d160f35829419c6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2020
ms.locfileid: "90025569"
---
# <a name="visual-studio-unrecoverable-process-error"></a>Неустранимая ошибка процесса в Visual Studio

В Visual Studio применяется несколько внепроцессных процессов для выполнения необходимых фоновых задач, таких как динамическое модульное тестирование, анализаторы кода и т. д. Эти процессы выполняются вне процесса для предоставления Visual Studio преимуществ производительности, таких как быстрое реагирование при выполнении ресурсоемких и продолжительных заданий. Кроме того, так как Visual Studio является 32-разрядным процессом, внепроцессный запуск процессов позволяет выделять операциям с интенсивным использованием памяти область памяти большего объема.

Если процесс *ServiceHub.RoslynCodeAnalysisService.exe* или *ServiceHub.RoslynCodeAnalysisService32.exe* завершается по какой-либо причине, появляется всплывающая строка со следующим сообщением:

**"К сожалению, произошла неустранимая ошибка процесса, используемого Visual Studio. Рекомендуется сохранить работу, а затем закрыть и перезапустить Visual Studio".**

Если вы видите это сообщение, необходимо сохранить работу и затем закрыть и перезапустить Visual Studio.

## <a name="list-of-processes"></a>Список процессов

Ниже приведен список процессов вне процесса, используемый в Visual Studio. Этот список включает в себя процессы, запускающиеся в определенных рабочих процессах или сценариях, и поэтому в большинстве случаев не все они выполняются одновременно.

- Microsoft.Alm.Shared.Remoting.RemoteContainer.dll
- Microsoft.CodeAnalysis.LiveUnitTesting.EntryPoint
- MSBuild.exe
- PerfWatson2.exe
- ScriptedSandbox64.exe
- ServiceHub.Host.CLR.x86.exe
- ServiceHub.Host.Node.x86.exe
- ServiceHub.IdentityHost.exe
- ServiceHub.RoslynCodeAnalysisService.exe
- ServiceHub.RoslynCodeAnalysisService32.exe
- ServiceHub.SettingsHost.exe
- ServiceHub.VSDetouredHost.exe
- VBCSCompiler.exe
- VsHub.exe
- vstest.discoveryengine.x86.exe
- WaAppAgent.exe
- WindowsAzureGuestAgent.exe
- WindowsAzureTelemetryService.exe

Если любой из этих процессов непредвиденно завершает работу, некоторые функциональные возможности в Visual Studio перестают работать. Для некоторых процессов потеря функциональности может быть незначительной. Другие процессы влияют на стабильность работы Visual Studio, и отображается сообщение об ошибке.

> [!NOTE]
> Если у вас возникла проблема, не указанная на этой странице, сообщите нам о ней с помощью средства [Сообщить о проблеме](../../ide/how-to-report-a-problem-with-visual-studio.md).Оно доступно как в Visual Studio Installer, так и в Visual Studio IDE.
