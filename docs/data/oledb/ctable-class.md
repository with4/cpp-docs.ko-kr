---
title: CTable 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CTable
- ATL.CTable
- CTable
dev_langs:
- C++
helpviewer_keywords:
- CTable class
ms.assetid: f13fdaa3-e198-4557-977d-54b0bbc3454d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e12ec9f7cc7db4da78df8f3b49ed4fdadef3f769
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100147"
---
# <a name="ctable-class"></a>CTable 클래스
단순 행 집합 (매개 변수 없이 하나)에 직접 액세스할 수 있는 방법을 제공 합니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class TAccessor = CNoAccessor, 
            template <typename T> class TRowset = CRowset>  
class CTable :  
   public CAccessorRowset <TAccessor, TRowset>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `TAccessor`  
 접근자 클래스입니다.  
  
 `TRowset`  
 행 집합 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[열기](../../data/oledb/ctable-open.md)|테이블을 엽니다.|  
  
## <a name="remarks"></a>설명  
 참조 [CCommand](../../data/oledb/ccommand-class.md) 행 집합에 액세스 하는 명령을 실행 하는 방법에 대 한 내용은 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx)