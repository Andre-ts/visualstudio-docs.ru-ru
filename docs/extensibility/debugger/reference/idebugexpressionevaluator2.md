---
title: IDebugExpressionEvaluator2 | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugExpressionEvaluator2 interface
ms.assetid: cebe649f-1c77-4d33-854f-30d4f00eceb4
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7041456bf0f3ae7930a73399d43dbf7cac6b3b32
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80729138"
---
# <a name="idebugexpressionevaluator2"></a>IDebugExpressionEvaluator2
> [!IMPORTANT]
> В Visual Studio 2015 такой способ реализации оценивающих выражений является устаревшим. Дополнительные сведения о реализации вычислителей выражений CLR см. в разделе средства [оценки выражений CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) и [Пример управляемого средства оценки выражений](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Представляет улучшенную версию средства оценки выражений (EE).

## <a name="syntax"></a>Синтаксис

```
IDebugExpressionEvaluator2 : IDebugExpressionEvaluator
```

## <a name="notes-for-implementers"></a>Примечания для разработчиков
 Этот интерфейс реализуется средством оценки выражений.

## <a name="methods"></a>Методы
 В дополнение к методам в интерфейсе [идебужекспрессионевалуатор](../../../extensibility/debugger/reference/idebugexpressionevaluator.md) этот интерфейс реализует следующие методы:

|Метод|Описание|
|------------|-----------------|
|[GetService](../../../extensibility/debugger/reference/idebugexpressionevaluator2-getservice.md)|Извлекает объект службы по заданному уникальному идентификатору.|
|[PreloadModules](../../../extensibility/debugger/reference/idebugexpressionevaluator2-preloadmodules.md)|Предварительно загружает модули, назначенные указанным поставщиком символов.|
|[SetCallback](../../../extensibility/debugger/reference/idebugexpressionevaluator2-setcallback.md)|Включает средство оценки выражений (EE) для указания интерфейса обратного вызова, который подсистема отладчика (DE) будет использовать для считывания параметров метрик.|
|[SetCorPath](../../../extensibility/debugger/reference/idebugexpressionevaluator2-setcorpath.md)|Задает путь к общеязыковой среде выполнения (CLR), загруженной в отладчике.|
|[SetIDebugIDECallback](../../../extensibility/debugger/reference/idebugexpressionevaluator2-setidebugidecallback.md)|Позволяет модулю отладки передавать обратный вызов средству оценки выражений во время инициализации.|
|[Завершение](../../../extensibility/debugger/reference/idebugexpressionevaluator2-terminate.md)|Останавливает и очищает средство оценки выражений.|

## <a name="requirements"></a>Требования
 Заголовок: ee. h

 Пространство имен: Microsoft. VisualStudio. Debugger. Interop

 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll
