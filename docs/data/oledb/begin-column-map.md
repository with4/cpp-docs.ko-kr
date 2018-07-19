---
title: BEGIN_COLUMN_MAP | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- BEGIN_COLUMN_MAP
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_COLUMN_MAP macro
ms.assetid: d6ffe633-e0da-4e33-8faa-f7f259d05420
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b6a619e36e3457902ce6ced07389ca8461499682
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094727"
---
# <a name="begincolumnmap"></a>BEGIN_COLUMN_MAP
열 맵 항목의 시작을 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
BEGIN_COLUMN_MAP(x)  
```  
  
#### <a name="parameters"></a>매개 변수  
 *x*  
 [in] `CAccessor`에서 파생된 사용자 레코드 클래스의 이름입니다.  
  
## <a name="remarks"></a>설명  
 이 매크로는 행 집합에 단일 접근자가 있는 경우에 사용됩니다. 행 집합에 여러 접근자가 있는 경우 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)을 사용합니다.  
  
 `BEGIN_COLUMN_MAP` 매크로는 `END_COLUMN_MAP` 매크로로 완료됩니다. 이 매크로는 사용자 레코드에 하나의 접근자만 필요한 경우에 사용됩니다.  
  
 열은 바인딩하려면 행 집합의 필드에 해당합니다.  
  
## <a name="example"></a>예제  
 다음은 열 및 매개 변수 맵의 샘플입니다.  
  
 <!--[!CODE [NVC_OLEDB_Consumer#16](../codesnippet/vs_snippets_cpp/nvc_oledb_consumer#16)]  -->
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역 함수에 대 한 OLE DB 소비자 템플릿](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)