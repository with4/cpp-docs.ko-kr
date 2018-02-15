---
title: COLUMN_ENTRY_PS_LENGTH | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- COLUMN_ENTRY_PS_LENGTH
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_ENTRY_PS_LENGTH macro
ms.assetid: d63ab895-a4df-4183-ac09-cf2311222408
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f3b37c9e8dead15fcc0b4cf0a9a8f6c0d1aac217
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="columnentrypslength"></a>COLUMN_ENTRY_PS_LENGTH
데이터베이스에서 특정 열에 대한 행 집합의 바인딩을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
COLUMN_ENTRY_PS_LENGTH(nOrdinal, nPrecision, nScale, data, length)  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
 `nOrdinal`  
 [in] 하나를 시작 열 번호입니다. 책갈피 열 0에 해당합니다.  
  
 `nPrecision`  
 [in] 바인딩하려는 열의 최대 정밀도입니다.  
  
 `nScale`  
 [in] 바인딩할 열의 배율입니다.  
  
 `data`  
 [in] 사용자 레코드에서 해당 데이터 멤버입니다.  
  
 *length*  
 [in] 열 길이에 바인딩할 변수입니다.  
  
## <a name="remarks"></a>설명  
 바인딩할 열의 정밀도 및 배율을 지정할 수 있습니다. 이 매크로 지원는 *길이* 변수입니다. 다음과 같은 위치에 사용됩니다.  
  
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
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN_ENTRY_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN_ENTRY_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN_ENTRY_LENGTH_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN_ENTRY_PS_LENGTH_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN_ENTRY_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN_ENTRY_PS_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)