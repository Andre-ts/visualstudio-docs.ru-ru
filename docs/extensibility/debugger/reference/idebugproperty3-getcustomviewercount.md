---
title: 'IDebugProperty3:: Жеткустомвиеверкаунт | Документация Майкрософт'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty3::GetCustomViewerCount
helpviewer_keywords:
- IDebugProperty3::GetCustomViewerCount
ms.assetid: dc5bb3e4-dc85-46e4-98fa-c6be8583b985
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 16cb623f58668362e5e308e1d66dfd6ca7c0fb8c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "80721181"
---
# <a name="idebugproperty3getcustomviewercount"></a>IDebugProperty3::GetCustomViewerCount
Возвращает число пользовательских средств просмотра, которые могут быть доступны для этого свойства.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetCustomViewerCount(
    ULONG* pcelt
);
```

```csharp
int GetCustomViewerCount(
    out uint pcelt
);
```

## <a name="parameters"></a>Параметры
`pcelt`\
заполняет Число пользовательских средств просмотра, доступных для этого свойства.

## <a name="return-value"></a>Возвращаемое значение
Возвращает значение `S_OK`, если выполнение прошло успешно; в противном случае возвращает код ошибки.

## <a name="remarks"></a>Remarks
Для поддержки визуализаторов типов этот метод пересылает вызов методу [жеткустомвиеверкаунт](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md) . Если средство оценки выражений также поддерживает пользовательские средства просмотра для типа этого свойства, этот метод добавляет число пользовательских средств просмотра к возвращаемому значению.

Подробные сведения о различиях между визуализаторами типов и пользовательскими средствами просмотра см. в разделе [Визуализатор типов и пользовательское средство просмотра](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md).

## <a name="example"></a>Пример
В следующем примере показано, как реализовать этот метод для объекта **кпроперти** , предоставляющего интерфейс [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) .

```cpp
STDMETHODIMP CProperty::GetCustomViewerCount(ULONG* pcelt)
{
    if (pcelt == NULL)
    {
        return E_POINTER;
    }

    if (GetVisualizerService())
    {
        return m_pIEEVisualizerService->GetCustomViewerCount(pcelt);
    }
    else
    {
        return E_NOTIMPL;
    }
}
```

## <a name="see-also"></a>См. также раздел
- [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)
- [GetCustomViewerCount](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md)
- [Визуализатор типов и пользовательское средство просмотра](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)
