---
title: "RMyProviderRowset의 상속 수정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "상속[C++]"
  - "RMyProviderRowset"
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RMyProviderRowset의 상속 수정
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

단순한 읽기 전용 공급자 예제에 `IRowsetLocate` 인터페이스를 추가하려면 **RMyProviderRowset**의 상속을 수정합니다.  **RMyProviderRowset**은 초기에 `CRowsetImpl`에서 상속하므로  **CRowsetBaseImpl**에서 상속하도록 수정해야 합니다.  
  
 상속을 수정하려면 `CMyRowsetImpl`이라는 새 클래스를 MyProviderRS.h에 만듭니다.  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage> >  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate > >  
{  
...  
};  
```  
  
 그런 다음 MyProviderRS.h의 COM 인터페이스 맵을 다음과 같이 편집합니다.  
  
```  
BEGIN_COM_MAP(CMyRowsetImpl)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 그러면 COM 인터페이스 맵이 만들어집니다. 이 COM 인터페이스 맵은 `IRowset`과 `IRowsetLocate` 두 인터페이스에 대해 모두 **QueryInterface**를 호출할 것을 `CMyRowsetImpl`에 알리는 맵입니다.  이 맵은 다른 행 집합 클래스에 대한 구현을 모두 가져오기 위해 OLE DB 탬플릿이 정의한 **CRowsetBaseImpl** 클래스에 `CMyRowsetImpl` 클래스를 다시 연결하고, `QueryInterface` 호출에 응답하여 **CRowsetBaseImpl**의 COM 맵을 검색할 것을 OLE DB 탬플릿에 알리는 COM\_INTERFACE\_ENTRY\_CHAIN 매크로를 사용합니다.  
  
 마지막으로 `CMyRowsetImpl`에서 상속하도록 다음과 같이 `RAgentRowset`을 수정하여 `RAgentRowset`을 `CMyRowsetBaseImpl`에 연결합니다.  
  
```  
class RAgentRowset : public CMyRowsetImpl<RAgentRowset, CAgentMan, CMyProviderCommand>  
```  
  
 이제 `RAgentRowset`이 `IRowsetLocate` 인터페이스를 사용하는 동시에 행 집합 클래스에 대한 나머지 구현을 이용할 수 있게 됩니다.  
  
 이 작업을 마치면 [소비자에게 반환되는 열을 동적으로 결정](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)할 수 있습니다.  
  
## 참고 항목  
 [단순한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)