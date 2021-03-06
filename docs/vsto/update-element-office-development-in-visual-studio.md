---
title: '&lt;&gt;элемент Update (разработка решений Office в Visual Studio)'
ms.date: 02/02/2017
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- update element
- <update> element
- application manifests [Office development in Visual Studio], <update> element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 241bddb8c79a01bb1ba6921486a4dc46d99940cc
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "85537388"
---
# <a name="ltupdategt-element-office-development-in-visual-studio"></a>&lt;&gt;элемент Update (разработка решений Office в Visual Studio)
  `update`Элемент указывает интервал, в течение которого решение будет проверять наличие обновлений.

## <a name="syntax"></a>Синтаксис

```xml
<update
  enabled>
  <expiration
    maximumAge
    unit
  />
</update>
```

## <a name="elements-and-attributes"></a>Элементы и атрибуты
 Элемент `update` является обязательным и находится в пространстве имен `vstav3` .

 Элемент `update` имеет перечисленные ниже атрибуты.

|Атрибут|Описание|
|---------------|-----------------|
|`enabled`|Обязательный. Задайте для параметра включено одно из следующих значений:<br /><br /> -   **значение true** для проверки наличия обновлений.<br />-   **значение false** , чтобы запретить проверку наличия обновлений.|

 Элемент `update` имеет указанные ниже дочерние элементы.

### <a name="expiration"></a>expiration
 Элемент `expiration` является обязательным и находится в пространстве имен `vstav3` . Этот элемент задает интервал, с которым решение проверяет наличие обновлений.

 Элемент `expiration` имеет перечисленные ниже атрибуты.

|Атрибут|Описание|
|---------------|-----------------|
|`maximumAge`| Обязательный. Задайте значение, равное целому числу.|
|`unit`|Обязательный. Задайте `unit` одно из следующих значений:<br /><br /> -   **суток**<br />-   **недели**<br />-   **неделю**|

## <a name="example-of-always-checking-for-updates"></a>Пример всегда проверять наличие обновлений

### <a name="description"></a>Описание
 В следующем примере кода показан `update` элемент, для которого установлено значение всегда проверять наличие обновлений в решениях Office.

### <a name="code"></a>Код

```xml
<vstav3:update enabled="true" />
```

## <a name="example-of-setting-a-default-update-interval"></a>Пример задания интервала обновления по умолчанию

### <a name="description"></a>Описание
 В следующем примере кода показан `update` элемент в манифесте приложения для решений Office. Этот пример кода является частью большого примера, приведенного в разделе [манифесты приложений для решений Office](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Код

```xml
<vstav3:update enabled="true">
    <vstav3:expiration maximumAge="7" unit="days" />
</vstav3:update>
```

## <a name="see-also"></a>См. также

- [Развертывание решения Office с помощью ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md)
- [Манифесты приложений для решений Office](../vsto/application-manifests-for-office-solutions.md)
- [Манифесты развертывания для решений Office](../vsto/deployment-manifests-for-office-solutions.md)
- [Манифест приложения ClickOnce](../deployment/clickonce-application-manifest.md)
