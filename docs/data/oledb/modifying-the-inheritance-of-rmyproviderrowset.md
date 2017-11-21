---
title: "RMyProviderRowset의 상속 수정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- RMyProviderRowset
- inheritance [C++]
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e8ecfe35d61762b8beaa217eaacc4202a588debb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="modifying-the-inheritance-of-rmyproviderrowset"></a>RMyProviderRowset의 상속 수정
추가 하는 `IRowsetLocate` 단순한 읽기 전용 공급자 예제 인터페이스를의 상속 수정 **RMyProviderRowset**합니다. 처음에 **RMyProviderRowset** 에서 상속 `CRowsetImpl`합니다. 상속 하도록 수정 해야 할 **CRowsetBaseImpl**합니다.  
  
 이렇게 하려면 새 클래스를 만든 `CMyRowsetImpl`, MyProviderRS.h의:  
  
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
  
 이제 다음과 같이 되도록 MyProviderRS.h의 COM 인터페이스 맵을 편집 합니다.  
  
```  
BEGIN_COM_MAP(CMyRowsetImpl)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 그렇기 때문에 알려 주는 COM 인터페이스 맵을 `CMyRowsetImpl` 를 호출할 **QueryInterface** 모두에 대 한는 `IRowset` 및 `IRowsetLocate` 인터페이스입니다. 모든 다른 행 집합에 대 한 구현을 가져올 클래스, 맵 링크는 `CMyRowsetImpl` 클래스에 다시는 **CRowsetBaseImpl** 여 OLE DB 템플릿 클래스를 정의 맵을 사용 알려 주는 COM_INTERFACE_ENTRY_CHAIN 매크로 COM을 검색 하도록 OLE DB 템플릿에 매핑할 **CRowsetBaseImpl** 대 한 응답으로 `QueryInterface` 호출 합니다.  
  
 마지막으로, 연결 `RAgentRowset` 를 `CMyRowsetBaseImpl` 수정 하 여 `RAgentRowset` 상속할 `CMyRowsetImpl`다음과 같이:  
  
```  
class RAgentRowset : public CMyRowsetImpl<RAgentRowset, CAgentMan, CMyProviderCommand>  
```  
  
 `RAgentRowset`이제 사용할 수는 `IRowsetLocate` 행 집합 클래스에 대 한 구현의 나머지 부분을 활용 하는 동안 인터페이스입니다.  
  
 이 작업을 수행할 수 있습니다 [소비자에 게 반환 되는 열을 동적으로 결정](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [단순한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)