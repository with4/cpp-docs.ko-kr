---
title: RMyProviderRowset의 상속 수정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- RMyProviderRowset
- inheritance [C++]
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 407406683f03dbba2d582b1ae24d5cc3bb8680a5
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39336467"
---
# <a name="modifying-the-inheritance-of-rmyproviderrowset"></a>RMyProviderRowset의 상속 수정
추가 하는 `IRowsetLocate` 단순한 읽기 전용 공급자 예제 인터페이스의 상속 수정, `RMyProviderRowset`합니다. 처음에 `RMyProviderRowset` 에서 상속 `CRowsetImpl`합니다. 상속 하도록 수정 해야 `CRowsetBaseImpl`합니다.  
  
 이렇게 하려면 새 클래스를 만듭니다 `CMyRowsetImpl`, MyProviderRS.h의:  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage>>  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate >>  
{  
...  
};  
```  
  
 이제 다음과 같이 되도록 MyProviderRS.h의 COM 인터페이스 맵을 편집 합니다.  
  
```cpp  
BEGIN_COM_MAP(CMyRowsetImpl)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 지시 하는 COM 인터페이스 맵을 만듭니다 `CMyRowsetImpl` 호출 `QueryInterface` 둘 다에 대해 합니다 `IRowset` 및 `IRowsetLocate` 인터페이스입니다. 다른 행 집합에 대 한 구현의 모든 클래스, 맵 링크는 `CMyRowsetImpl` 클래스를는 `CRowsetBaseImpl` map의 COM 맵에 검색 하려면 OLE DB 템플릿 알려 주는 COM_INTERFACE_ENTRY_CHAIN 매크로 사용 하 여; OLE DB 템플릿에 정의 된 클래스 `CRowsetBaseImpl` 에 대 한 응답을 `QueryInterface` 호출 합니다.  
  
 마지막으로 연결 `RAgentRowset` 하 `CMyRowsetBaseImpl` 수정 하 여 `RAgentRowset` 상속할 `CMyRowsetImpl`같이:  
  
```cpp  
class RAgentRowset : public CMyRowsetImpl<RAgentRowset, CAgentMan, CMyProviderCommand>  
```  
  
 `RAgentRowset` 이제 사용할 수는 `IRowsetLocate` 행 집합 클래스 구현의 나머지 부분을 활용 하는 인터페이스입니다.  
  
 이 작업을 수행할 수 있습니다 [소비자에 게 반환 되는 열을 동적으로 결정](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [단순한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)