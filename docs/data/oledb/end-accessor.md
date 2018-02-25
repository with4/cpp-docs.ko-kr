---
title: END_ACCESSOR | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- END_ACCESSOR
dev_langs:
- C++
helpviewer_keywords:
- END_ACCESSOR macro
ms.assetid: 26f74167-68c4-4909-a474-73dc7ebc9542
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2907823c09c481c648c648d86df676fc5c435955
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="endaccessor"></a>END_ACCESSOR
접근자 항목의 끝을 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
END_ACCESSOR()  
  
```  
  
## <a name="remarks"></a>설명  
 지정 해야 행 집합에서 여러 접근자 `BEGIN_ACCESSOR_MAP` 사용 하는 `BEGIN_ACCESSOR` 각 접근자에 대 한 매크로입니다. `BEGIN_ACCESSOR` 매크로는 `END_ACCESSOR` 매크로로 완료됩니다. `BEGIN_ACCESSOR_MAP` 매크로로 완료 됩니다는 `END_ACCESSOR_MAP` 매크로입니다.  
  
## <a name="example"></a>예  
 참조 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역 함수에 대 한 OLE DB 소비자 템플릿](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)