---
title: CEnumerator 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CEnumerator
dev_langs:
- C++
helpviewer_keywords:
- CEnumerator class
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2b7e390212da53f85cb50dd5bb151ea6740784b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cenumerator-class"></a>CEnumerator 클래스
노출 하는 OLE DB 열거자 개체를 사용 하 여는 [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) 모든 데이터 원본 및 열거자를 설명 하는 행 집합을 반환 하는 인터페이스입니다.  
  
## <a name="syntax"></a>구문

```cpp
class CEnumerator :   
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>  
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[찾기](../../data/oledb/cenumerator-find.md)|지정 된 이름의 하나 찾고 사용 가능한 공급자 (데이터 원본)에서 검색 합니다.|  
|[GetMoniker](../../data/oledb/cenumerator-getmoniker.md)|검색 된 `IMoniker` 현재 레코드에 대 한 인터페이스입니다.|  
|[열기](../../data/oledb/cenumerator-open.md)|열거자를 엽니다.|  
  
## <a name="remarks"></a>설명  
 검색할 수 있습니다는 **ISourcesRowset** 이 클래스에서 간접적으로 데이터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [DBViewer](../../visual-cpp-samples.md)   
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)