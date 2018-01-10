---
title: COLUMN_ENTRY_TYPE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COLUMN_ENTRY_TYPE
dev_langs: C++
helpviewer_keywords: COLUMN_ENTRY_TYPE macro
ms.assetid: ac424261-ff6c-443b-a197-2cec8d78d738
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cc2501f38ca93192bd0d74a3d49ca829b19cc1ce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="columnentrytype"></a>COLUMN_ENTRY_TYPE
데이터베이스의 특정 열에 대 한 바인딩을 나타냅니다. 지원 `type` 매개 변수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
COLUMN_ENTRY_TYPE (  
nOrdinal  
,   
wType  
,   
data  
 )  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nOrdinal`  
 [in] 열 번호입니다.  
  
 `wType`  
 [in] 데이터 형식 열 항목입니다.  
  
 `data`  
 [in] 사용자 레코드에서 해당 데이터 멤버입니다.  
  
## <a name="remarks"></a>설명  
 이 매크로 라는 특수 한 유형의 [COLUMN_ENTRY](../../data/oledb/column-entry.md) 데이터 형식을 지정 하는 방법을 제공 하는 매크로입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역 함수에 대 한 OLE DB 소비자 템플릿](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)