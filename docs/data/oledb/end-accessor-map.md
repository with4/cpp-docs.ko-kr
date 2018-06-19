---
title: END_ACCESSOR_MAP | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- END_ACCESSOR_MAP
dev_langs:
- C++
helpviewer_keywords:
- END_ACCESSOR_MAP macro
ms.assetid: ede813c7-46c9-48a6-aa1a-8ebf38e92023
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 647e581a86564221ad409caf9addd03ae3d11fb1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101567"
---
# <a name="endaccessormap"></a>END_ACCESSOR_MAP
접근자 맵 항목의 끝을 표시 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
END_ACCESSOR_MAP()  
  
```  
  
## <a name="remarks"></a>설명  
 지정 해야 행 집합에서 여러 접근자 `BEGIN_ACCESSOR_MAP` 사용 하는 `BEGIN_ACCESSOR` 각 접근자에 대 한 매크로입니다. `BEGIN_ACCESSOR` 매크로는 `END_ACCESSOR` 매크로로 완료됩니다. `BEGIN_ACCESSOR_MAP` 매크로로 완료 됩니다는 `END_ACCESSOR_MAP` 매크로입니다.  
  
## <a name="example"></a>예제  
 참조 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역 함수에 대 한 OLE DB 소비자 템플릿](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)