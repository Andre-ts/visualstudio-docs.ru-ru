---
title: Использование модели автоматизации | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK], automation model
ms.assetid: 0c7f7889-fbfb-4b19-804f-b742138baecd
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d014627161666473d3b674f72cfec339a66fdc05
ms.sourcegitcommit: 4b29efeb3a5f05888422417c4ee236e07197fb94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2020
ms.locfileid: "90012494"
---
# <a name="using-the-automation-model"></a>Использование модели автоматизации
После подключения VSPackage к службе автоматизации можно получить свойства и методы, вызвав <xref:EnvDTE.DTEClass.GetObject%2A> метод для <xref:EnvDTE._DTE> объекта, передав строку, представляющую объект, который вы хотите получить.

## <a name="obtaining-project-objects"></a>Получение объектов проекта
 Ниже приведены два примера кода, демонстрирующих, как потребитель автоматизации получает объекты автоматизации проекта. Сведения о том, как получить объект DTE, см. в разделе [инструкции. получение ссылок на объекты DTE и DTE2](/previous-versions/68shb4dw(v=vs.140)).

```vb
Sub DoAutomation()
    Dim MyProjects As Projects
    MyProjects = DTE.GetObject("AcmeProject")
End Sub
```

```cpp
void DoAutomation(void)
{
  CComQIPtr<Projects> pMyPkg; // Use an IDispatch-derived object type.
    pMyPkg = pDTE->GetObject("AcmeProjects");

   // The '=' performs a Query Interface.
   // Assumes pDTE is already available as a global.
   // Use pMyPkg to access your projects object's properties and methods.
}

```

 На этом этапе можно использовать стандартные объекты проекта, которые являются частью определенного VSPackage, чтобы переместить модель иерархии.

 В следующем примере кода показано, как получить пользовательский объект, являющийся свойством пользовательского типа проекта.

```vb
Dim MyPrj As Project
Dim MyPrjItem As ProjectItem
Dim objMyObject as MyExtendedObject

MyPrj = MyProjects.Item(1) 'use the Projects collection to get a project
objMyObject = MyPrj.Object 'You call .Object to get to special Project
                           'implementation
objMyObject.MySpecialMethodOrProperty
```

 В следующем коде перечислены имена всех свойств в [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] параметре среда **Общие** в меню **Сервис** .

```vb
dim objDTE
dim objEnv
set objDTE = CreateObject("VisualStudio.DTE")
set objEnv = objDTE.Properties("Environment", "General")
for each obj in ObjEnv
MsgBox obj.Name
Next

```

## <a name="see-also"></a>См. также
- <xref:EnvDTE.DTEClass.GetObject%2A>