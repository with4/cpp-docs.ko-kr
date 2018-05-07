---
title: COLUMN_NAME | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_NAME
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_NAME macro
ms.assetid: a213b9a0-2148-4a08-9111-d9fa8fdec462
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f60acfac21e003f6a548c5702ebb975a458a93cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="columnname"></a>COLUMN_NAME
행 집합의 특정 열에는 행 집합의 바인딩을 나타냅니다. 비슷한 [COLUMN_ENTRY](../../data/oledb/column-entry.md)제외 하 고이 매크로 열 번호 대신 열 이름을 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
COLUMN_NAME(pszName, data)  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszName`  
 [in] 열 이름에 대 한 포인터입니다. 이름에는 유니코드 문자열 이어야 합니다. 예를 들어, 이름 앞에 'L'을 배치 하 여이 수행할 수 있습니다: `L"MyColumn"`합니다.  
  
 `data`  
 [in] 사용자 레코드에서 해당 데이터 멤버입니다.  
  
## <a name="remarks"></a>설명  
 **COLUMN_NAME_\***  와 동일한 위치에 매크로 사용 [COLUMN_ENTRY](../../data/oledb/column-entry.md):  
  
-   사이 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) 및 [END_COLUMN_MAP](../../data/oledb/end-column-map.md) 매크로입니다.  
  
-   사이 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) 및 [END_ACCESSOR](../../data/oledb/end-accessor.md) 매크로입니다.  
  
-   사이 [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) 및 [END_PARAM_MAP](../../data/oledb/end-param-map.md) 매크로입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역 함수에 대 한 OLE DB 소비자 템플릿](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_NAME_EX](../../data/oledb/column-name-ex.md)   
 [COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN_NAME_LENGTH_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN_NAME_PS_LENGTH](../../data/oledb/column-name-ps-length.md)   
 [COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN_NAME_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN_NAME_TYPE_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN_NAME_TYPE_SIZE](../../data/oledb/column-name-type-size.md)   
 [COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)