---
title: CMyProviderSession (MyProviderSess.H) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cmyprovidersession
- myprovidersess.h
dev_langs:
- C++
helpviewer_keywords:
- CMyProviderSession class in MyProviderSess.H
- OLE DB providers, wizard-generated files
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c244d77a0e299f4a09de985e11c7537a9fb7e5ff
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="cmyprovidersession-myprovidersessh"></a>CMyProviderSession(MyProviderSess.H)
MyProviderSess.H 선언 및 OLE DB 세션 개체에 대 한 구현을 포함합니다. 데이터 원본 개체 세션 개체를 만들고 소비자 및 공급자 간의 대화를 나타냅니다. 여러 개의 동시 세션 하나의 데이터 원본에 대 한 열 수 있습니다. 에 대 한 상속 목록 `CMyProviderSession` 따릅니다.  
  
```cpp
/////////////////////////////////////////////////////////////////////////  
// CMyProviderSession  
class ATL_NO_VTABLE CMyProviderSession :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public IGetDataSourceImpl<CMyProviderSession>,  
   public IOpenRowsetImpl<CMyProviderSession>,  
   public ISessionPropertiesImpl<CMyProviderSession>,  
   public IObjectWithSiteSessionImpl<CMyProviderSession>,  
   public IDBSchemaRowsetImpl<CMyProviderSession>,  
   public IDBCreateCommandImpl<CMyProviderSession, CMyProviderCommand>  
```  
  
 세션 개체에서 상속 **IGetDataSource**, `IOpenRowset`, **ISessionProperties**, 및 **IDBCreateCommand**합니다. **IGetDataSource** 이 인터페이스는 세션을 만든 데이터 원본을 검색을 허용 합니다. 만든 데이터 원본 또는 데이터 원본을 제공할 수 있는 기타 정보 속성을 가져오려면 해야 할 경우에 유용 합니다. **ISessionProperties** 인터페이스는 세션에 대 한 모든 속성을 처리 합니다. `IOpenRowset` 및 **IDBCreateCommand** 인터페이스는 데이터베이스 작업을 수행 하는 데 사용 됩니다. 공급자 명령을 지 원하는 경우 구현에서 **IDBCreateCommand** 인터페이스입니다. 명령을 실행할 수 있는 명령 개체를 만들 사용 됩니다. 항상 공급자를 구현 하는 `IOpenRowset` 개체입니다. 단순 행 집합 공급자에서 생성 하는 데 사용 됩니다. 기본 행 집합인 것 (예를 들어 `"select * from mytable"`) 공급자에서입니다.  
  
 마법사에 세 개의 세션 클래스도 생성: `CMyProviderSessionColSchema`, `CMyProviderSessionPTSchema`, 및 `CMyProviderSessionTRSchema`합니다. 이러한 세션은 스키마 행 집합에 사용 됩니다. 스키마 행 집합 공급자는 소비자가 실행 한 쿼리 또는 fetch 데이터 소비자에 게 메타 데이터를 반환 하기 수 있도록 합니다. 메타 데이터를 인출 하는 것은 공급자 기능을 검색 하는 보다 훨씬 빠를 수 있습니다.  
  
 사용 하려면 OLE DB 사양을 구현 하는 공급자는 **IDBSchemaRowset** 인터페이스 지원 3 스키마 행 집합 형식과: **DBSCHEMA_COLUMNS**, **DBSCHEMA_PROVIDER_TYPES** , 및 `DBSCHEMA_TABLES`합니다. 각 스키마 행 집합에 대 한 구현을 생성 됩니다. 마법사에 의해 생성 된 각 클래스에 포함 되어 있는 `Execute` 메서드. 이 `Execute` 메서드를 데이터 테이블, 열 및 데이터 형식에 대 한 지 원하는 공급자를 반환할 수 있습니다. 이 데이터는 컴파일 타임에 일반적으로 알려져 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [공급자 마법사가 생성하는 파일](../../data/oledb/provider-wizard-generated-files.md)