---
title: 'IDebugProcess3:: Execute | Документация Майкрософт'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess3::Execute
helpviewer_keywords:
- IDebugProcess3::Execute
ms.assetid: d831cd81-d7bf-4172-8517-aa699867791f
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: baa607e62732cdf0e04413e07966658bb6a0b8f4
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "86386515"
---
# <a name="idebugprocess3execute"></a>IDebugProcess3::Execute
Возобновляет выполнение этого процесса из остановленного состояния. Все предыдущие состояния выполнения (например, шаг) очищаются, и процесс начинает выполняться снова.

> [!NOTE]
> Этот метод следует использовать вместо [EXECUTE](../../../extensibility/debugger/reference/idebugprogram2-execute.md).

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT Execute(
   IDebugThread2* pThread
);
```

```csharp
int Execute(
   IDebugThread2 pThread
);
```

## <a name="parameters"></a>Параметры
`pThread`\
окне Объект [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) , представляющий выполняемый поток.

## <a name="return-value"></a>Возвращаемое значение
 В случае успеха возвращает `S_OK` ; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks
 Когда пользователь запускает выполнение из остановленного состояния в потоке другого процесса, этот метод вызывается в этом процессе. Этот метод также вызывается, когда пользователь выбирает команду **запуска** из меню **Отладка** в интегрированной среде разработки. Реализация этого метода может быть такой же простой, как вызов метода [Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md) в текущем потоке процесса.

> [!WARNING]
> Не отправляйте событие остановки или мгновенное (синхронное) событие в [событие](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) при обработке этого вызова; в противном случае отладчик может перестать отвечать на запросы.

## <a name="see-also"></a>См. также раздел
- [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [Возобновить](../../../extensibility/debugger/reference/idebugthread2-resume.md)
- [Событие](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
