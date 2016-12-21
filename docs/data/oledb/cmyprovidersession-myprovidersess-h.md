---
title: "CMyProviderSession(MyProviderSess.H) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cmyprovidersession"
  - ""myprovidersess.h""
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MyProviderSess.H의 CMyProviderSession 클래스"
  - "OLE DB 공급자, 마법사에서 생성된 파일"
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderSession(MyProviderSess.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MyProviderSess.H에는 OLE DB 세션 개체에 대한 선언과 구현이 있습니다.  데이터 소스 개체는 세션 개체를 만들고 소비자와 공급자 사이의 대화를 나타냅니다.  데이터 소스 하나에 대해 몇 개의 동시 세션을 열 수 있습니다.  `CMyProviderSession`의 상속 목록은 다음과 같습니다.  
  
```  
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
  
 세션 개체는 **IGetDataSource**, `IOpenRowset`, **ISessionProperties** 및 **IDBCreateCommand**에서 상속합니다.  **IGetDataSource** 인터페이스는 세션이 그 세션을 만든 데이터 소스를 검색할 수 있도록 합니다.  이 인터페이스는 자신이 만든 데이터 소스의 속성을 보거나 데이터 소스가 제공하는 다른 정보를 보려고 할 때 유용합니다.  **ISessionProperties** 인터페이스는 세션의 모든 속성을 처리합니다.  `IOpenRowset`과 **IDBCreateCommand** 인터페이스는 데이터베이스 작업을 하는 데 사용됩니다.  공급자가 명령을 지원하면 **IDBCreateCommand** 인터페이스를 구현합니다.  이 인터페이스는 명령을 실행하는 명령 개체를 만드는 데 사용됩니다.  `IOpenRowset`은 공급자가 항상 구현하는 개체로서,  공급자로부터 간단한 행 집합을 생성하는 데 사용됩니다.  이 행 집합이 공급자의 기본 행 집합\(예: `"select * from mytable"`\)이 됩니다.  
  
 또한 마법사는 `CMyProviderSessionColSchema`, `CMyProviderSessionPTSchema` 및 `CMyProviderSessionTRSchema`라는 세 개의 세션 클래스를 생성하며,  이러한 세션은 스키마 행 집합에 사용됩니다.  스키마 행 집합은 소비자가 쿼리를 실행하거나 데이터를 페치하지 않아도 공급자가 소비자에게 메타데이터를 반환할 수 있도록 합니다.  메타데이터를 페치하는 것이 이에 해당하는 공급자 기능을 찾는 것보다 훨씬 빠릅니다.  
  
 OLE DB 사양은 **IDBSchemaRowset** 인터페이스를 구현하는 공급자가 **DBSCHEMA\_COLUMNS**, **DBSCHEMA\_PROVIDER\_TYPES** 및 `DBSCHEMA_TABLES`라는 세 개의 스키마 행 집합 형식을 지원하도록 명시합니다.  마법사가 각 스키마 행 집합에 대한 구현을 생성합니다.  마법사가 생성한 각 클래스에는 `Execute` 메서드가 있습니다.  이 `Execute` 메서드를 통해 사용자가 지원하는 테이블, 열 및 데이터 형식에 대한 데이터를 공급자에게 반환할 수 있습니다.  이 데이터는 일반적으로 컴파일 타임에 알려집니다.  
  
## 참고 항목  
 [공급자 마법사가 생성하는 파일](../../data/oledb/provider-wizard-generated-files.md)