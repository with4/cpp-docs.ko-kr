---
title: CArrayRowset 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CArrayRowset<TAccessor>
- ATL.CArrayRowset
- CArrayRowset
- ATL::CArrayRowset
- ATL::CArrayRowset<TAccessor>
dev_langs:
- C++
helpviewer_keywords:
- CArrayRowset class
ms.assetid: 511427e1-73ca-4fd8-9ba1-ae9463557cb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 691776f39c54e843cec478c3c42871e7b7e81da1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="carrayrowset-class"></a>CArrayRowset 클래스
배열 구문을 사용 하 여 행 집합의 요소를 액세스 합니다.  
  
## <a name="syntax"></a>구문

```cpp
template < class TAccessor >  
class CArrayRowset :   
   public CVirtualBuffer <TAccessor>,   
   protected CBulkRowset <TAccessor>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `TAccessor`  
 접근자 클래스를 사용 하는 행 집합의 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[CArrayRowset](../../data/oledb/carrayrowset-carrayrowset.md)|생성자입니다.|  
|[스냅숏](../../data/oledb/carrayrowset-snapshot.md)|메모리에 전체 행 집합을 읽습니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[연산자&#91;&#93;](../../data/oledb/carrayrowset-operator.md)|행 집합의 요소에 액세스합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|[CArrayRowset::m_nRowsRead](../../data/oledb/carrayrowset-m-nrowsread.md)|이미 읽은 행 수를 지정 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CRowset 클래스](../../data/oledb/crowset-class.md)