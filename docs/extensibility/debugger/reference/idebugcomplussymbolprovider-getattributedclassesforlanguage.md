---
title: IDebugComPlusSymbolProvider::GetAttributedClassesForLanguage
titleSuffix: ''
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- GetAttributedClassesForLanguage
- IDebugComPlusSymbolProvider::GetAttributedClassesForLanguage
ms.assetid: e5b1b8b6-52a6-4ade-9a36-644abfa9f4b2
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 18f91e8df525cb861c9d1053b1f944352944a355
ms.sourcegitcommit: 4ae5e9817ad13edd05425febb322b5be6d3c3425
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2020
ms.locfileid: "90037384"
---
# <a name="idebugcomplussymbolprovidergetattributedclassesforlanguage"></a>IDebugComPlusSymbolProvider::GetAttributedClassesForLanguage
Извлекает классы с указанным атрибутом, реализованным в указанном языке программирования.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetAttributedClassesForLanguage (
    GUID               guidLanguage,
    LPOLESTR           pstrAttribute,
    IEnumDebugFields** ppEnum
);
```

```csharp
int GetAttributedClassesForLanguage (
    Guid                 guidLanguage,
    string               pstrAttribute,
    out IEnumDebugFields ppEnum
);
```

## <a name="parameters"></a>Параметры
`guidLanguage`\
окне Уникальный идентификатор для языка.

`pstrAttribute`\
окне Строка атрибута.

`ppEnum`\
заполняет Возвращает перечисление классов атрибутов.

## <a name="return-value"></a>Возвращаемое значение
Возвращает значение `S_OK`, если выполнение прошло успешно; в противном случае возвращает код ошибки.

## <a name="example"></a>Пример
В следующем примере показано, как реализовать этот метод для объекта **кдебугсимболпровидер** , предоставляющего интерфейс [идебугкомплуссимболпровидер](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md) .

```cpp
HRESULT CDebugSymbolProvider::GetAttributedClassesForLanguage(
    GUID guidLanguage,
    __in_z LPOLESTR pstrAttribute,
    IEnumDebugFields** ppEnum
)
{
    HRESULT hr = S_OK;
    CFieldList listFields;
    CModIter ModIter;
    CModule* pModule; // the iterator owns the reference
    ULONG cClasses = 0;
    DWORD iTypeDef = 0;
    mdTypeDef* rgTypeDefs = NULL;
    IDebugField** rgFields = NULL;
    DWORD ctField = 0;
    CEnumDebugFields* pEnumFields = NULL;

    ASSERT(IsValidObjectPtr(this, CDebugSymbolProvider));
    ASSERT(IsValidWritePtr(ppEnum, IEnumDebugFields*));

    METHOD_ENTRY( CDebugSymbolProvider::GetAttributedClassesForLanguage );

    IfFalseGo( ppEnum, E_INVALIDARG );
    *ppEnum = NULL;

    // For Each Module - call EnumFields
    IfFailGo( GetModuleIter(&ModIter) );

    // Find the Max number of classes
    while (ModIter.GetNext(&pModule))
    {
        CComPtr<IMetaDataImport> pMetaData;
        HCORENUM hEnum = 0;
        ULONG cTypeDefs;
        ULONG cEnum;

        pModule->GetMetaData( &pMetaData );

        IfFailGo( pMetaData->EnumTypeDefs( &hEnum,
                                           NULL,
                                           0,
                                           &cTypeDefs ) );
        IfFailGo( pMetaData->CountEnum( hEnum, &cEnum ) );
        cClasses += cEnum;
    }

    IfNullGo( rgTypeDefs = new mdTypeDef[cClasses], E_OUTOFMEMORY );
    IfNullGo( rgFields = new IDebugField * [cClasses], E_OUTOFMEMORY );

    ModIter.Reset();

    // Create the classes
    while (ModIter.GetNext(&pModule))
    {
        CComPtr<IMetaDataImport> pMetaData;
        HCORENUM hEnum = 0;
        ULONG cTypeDefs;
        ULONG cEnum;
        const void* pUnused;
        ULONG cbUnused;

        pModule->GetMetaData( &pMetaData );

        IfFailGo( pMetaData->EnumTypeDefs( &hEnum,
                                           NULL,
                                           0,
                                           &cTypeDefs ) );
        IfFailGo( pMetaData->CountEnum( hEnum, &cEnum ) );
        IfFailGo( pMetaData->EnumTypeDefs( &hEnum,
                                           rgTypeDefs,
                                           cEnum,
                                           &cTypeDefs ) );

        pMetaData->CloseEnum(hEnum);
        hEnum = NULL;

        for ( iTypeDef = 0; iTypeDef < cTypeDefs; iTypeDef++)
        {

            if (pMetaData->GetCustomAttributeByName( rgTypeDefs[iTypeDef],
                    pstrAttribute,
                    &pUnused,
                    &cbUnused ) == S_OK)
            {
                // Only return classes implemeted in the correct language

                if (pModule->ClassImplementedInLanguage( rgTypeDefs[iTypeDef],
                        guidLanguage) )
                {
                    if (CreateClassType( pModule->GetID(),
                                         rgTypeDefs[iTypeDef],
                                         rgFields + ctField) == S_OK)
                    {
                        ctField++;
                    }
                    else
                    {
                        ASSERT(!"Failed to Create Attributed Class");
                    }
                }
            }
        }
    }

    IfNullGo( pEnumFields = new CEnumDebugFields, E_OUTOFMEMORY );
    IfFailGo( pEnumFields->Initialize(rgFields, ctField) );
    IfFailGo( pEnumFields->QueryInterface( __uuidof(IEnumDebugFields),
                                           (void**) ppEnum ) );

Error:

    METHOD_EXIT( CDebugSymbolProvider::GetAttributedClassesForLanguage, hr );

    DELETERG( rgTypeDefs );

    for ( iTypeDef = 0; iTypeDef < ctField; iTypeDef++)
    {
        RELEASE( rgFields[iTypeDef] );
    }

    DELETERG( rgFields );
    RELEASE( pEnumFields );

    return hr;
}
```

## <a name="see-also"></a>См. также раздел
- [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)
