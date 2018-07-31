---
title: CStreamRowset 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CStreamRowset<TAccessor>
- ATL::CStreamRowset
- CStreamRowset
- ATL.CStreamRowset<TAccessor>
- ATL.CStreamRowset
- CStreamRowset::CStreamRowset
- CStreamRowset.CStreamRowset
- ATL.CStreamRowset.CStreamRowset
- ATL::CStreamRowset::CStreamRowset
- CStreamRowset
- CStreamRowset<TAccessor>::CStreamRowset
- ATL::CStreamRowset<TAccessor>::CStreamRowset
- CStreamRowset<TAccessor>.Close
- ATL.CStreamRowset<TAccessor>.Close
- CStreamRowset::Close
- CStreamRowset<TAccessor>::Close
- ATL::CStreamRowset::Close
- ATL.CStreamRowset.Close
- ATL::CStreamRowset<TAccessor>::Close
- CStreamRowset.Close
dev_langs:
- C++
helpviewer_keywords:
- CStreamRowset class
- CStreamRowset class, constructor
- Close method
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8b9f1c7aef4116ae057d771e66b5027c5783f64e
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338014"
---
# <a name="cstreamrowset-class"></a>CStreamRowset 클래스
에 사용 된 `CCommand` 또는 `CTable` 선언 합니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class TAccessor = CAccessorBase>  
class CStreamRowset  
```  
  
### <a name="parameters"></a>매개 변수  
 *TAccessor*  
 접근자 클래스입니다.  

## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[CStreamRowset](#cstreamrowset)|생성자입니다. 인스턴스화하고 초기화는 `CStreamRowset` 개체입니다.|  
|[닫기](#close)|릴리스를 [ISequentialStream](https://msdn.microsoft.com/library/ms718035.aspx) 클래스에 대 한 인터페이스 포인터입니다.|  
  
## <a name="remarks"></a>설명  
 사용 하 여 `CStreamRowset` 에 사용자 `CCommand` 또는 `CTable` 선언 예제:  
  
 [!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]  
  
 또는  
  
 [!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]  
  
 `ICommand::Execute` 반환 합니다는 `ISequentialStream` 에 저장 된 포인터 `m_spStream`합니다. 그런 다음 사용은 `Read` XML 형식에서 (유니코드 문자열) 데이터를 검색 하는 방법. 예를 들어:  
  
 [!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]  
  
 SQL Server 2000 XML 서식에서 수행 하 고 모든 열과 하나의 XML 문자열로 행 집합의 모든 행 반환 됩니다.  
  
> [!NOTE]
>  이 기능은 SQL Server 2000과만 작동합니다.  
  
## <a name="cstreamrowset"></a> Cstreamrowset:: Cstreamrowset
인스턴스화하고 초기화는 `CStreamRowset` 개체입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
CStreamRowset();  
```  

## <a name="close"></a> Cstreamrowset:: Close
릴리스를 [ISequentialStream](https://msdn.microsoft.com/library/ms718035.aspx) 클래스에 대 한 인터페이스 포인터입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
void Close();   
```  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)