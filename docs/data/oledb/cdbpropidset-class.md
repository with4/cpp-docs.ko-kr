---
title: CDBPropIDSet 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBPropIDSet
- ATL.CDBPropIDSet
- ATL::CDBPropIDSet
dev_langs:
- C++
helpviewer_keywords:
- CDBPropIDSet class
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 67bfd11a46d8e0c852c1881ff8874b7fbd817164
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cdbpropidset-class"></a>CDBPropIDSet 클래스
상속 되는 **DBPROPIDSET** 구조체를 추가 하는 키 필드를 초기화 하는 생성자와 [AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md) 메서드에 액세스 합니다.  
  
## <a name="syntax"></a>구문

```cpp
class CDBPropIDSet : public tagDBPROPIDSET  
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md)|속성 ID 집합에는 속성을 추가합니다.|  
|[CDBPropIDSet](../../data/oledb/cdbpropidset-cdbpropidset.md)|생성자입니다.|  
|[SetGUID](../../data/oledb/cdbpropidset-setguid.md)|속성 ID의 GUID 집합를 설정 합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[operator =](../../data/oledb/cdbpropidset-operator-equal.md)|할당 한 속성 ID의 내용을 다른로 설정합니다.|  
  
## <a name="remarks"></a>설명  
 OLE DB 소비자가 사용 하 여 **DBPROPIDSET** 는 소비자가 속성 정보를 가져올 속성 Id의 배열을 전달 하는 구조입니다. 단일에서 식별 된 속성 [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) 구조 한 속성 집합에 속합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)