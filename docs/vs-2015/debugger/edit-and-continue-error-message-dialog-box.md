---
title: Изменить и продолжить-диалоговое окно ошибки сообщения | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.ENC.SupportedButNotAvaiable
- vs.debug.ENC.CannotEditWhileException
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Edit and Continue Error Message dialog box
ms.assetid: f98c91c0-447a-4533-85b6-87170a0dc4c3
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d649df9584fc06ee08b7a7d1e846597c12519019
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47560903"
---
# <a name="edit-and-continue-error-message-dialog-box"></a>Диалоговое окно сообщения об ошибке "Изменить и продолжить"
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [изменить и продолжить появления сообщения об ошибке](https://docs.microsoft.com/visualstudio/debugger/edit-and-continue-error-message-dialog-box).  
  
Это диалоговое окно отображается при отладке на языке, который поддерживает изменить и продолжить, но **изменить и продолжить** не поддерживается для типа были внесены изменения кода. Сообщение об ошибке в окне содержит более подробное объяснение. Ниже перечислены причины, по которым может отображаться это диалоговое окно.  
  
-   Предпринята попытка изменить управляемый код, когда была включена отладка неуправляемого кода. Операция "Изменить и продолжить" не работает при отладке в смешанном режиме.  
  
-   Предпринята попытка изменить код SQL Server.  
  
-   Предпринята попытка изменить код во время отладки дампа программы "Доктор Watson;  
  
-   Предпринята попытка изменить код после возникло необработанное исключение и параметр "**Очищать стек вызовов от кадров необработанных исключений**" не был выбран.  
  
-   Предпринята попытка изменить код во время отладки встроенного приложения среды выполнения.  
  
-   Предпринята попытка изменить код в программе, которая привязана вместо запуска из **Отладка** меню.  
  
-   Предпринята попытка изменить оптимизированный код.  
  
-   Предпринята попытка изменить управляемый код для 64-разрядного приложения. Если необходимо использовать операцию "Изменить и продолжить", нужно задать целевую архитектуру x86 (*Проекта* **свойства**, **компиляции** вкладке **Дополнительные параметры компилятора** параметр.).  
  
-   Предпринята попытка изменить код в сборке, которая была изменена во время отладки и перезагружена.  
  
-   Предпринята попытка изменить код в сборке, которая не была загружена.  
  
-   Была начата отладка старой версии приложения (поскольку при сборке новой версии возникли ошибки).  
  
-   Предпринята попытка изменить код во время его выполнения.  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **OK**  
 Выход из диалогового окна и отмена последней попытки изменения.  
  
## <a name="see-also"></a>См. также  
 [Поддерживаемые изменения кода (C++)](../debugger/supported-code-changes-cpp.md)


