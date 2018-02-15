---
title: "CRestrictions 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CRestrictions
- CRestrictions
- ATL.CRestrictions
dev_langs:
- C++
helpviewer_keywords:
- CRestrictions class
ms.assetid: 0aaa2364-641c-4318-b110-7446aada4b4f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: df38bc85775c67084e8952210ab368d930439114
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="crestrictions-class"></a>CRestrictions 클래스
스키마 행 집합에 대 한 제한 사항을 지정할 수 있도록 하는 제네릭 클래스입니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class T, short nRestrictions, const GUID* pguid>  
class CRestrictions : 
        public CSchemaRowset <T, nRestrictions>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 접근자에 사용 되는 클래스입니다.  
  
 `nRestrictions`  
 스키마 행 집합에 대 한 제한 열의 수입니다.  
  
 `pguid`  
 스키마에 대 한 GUID에 대 한 포인터입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[열기](../../data/oledb/crestrictions-open.md)|결과 사용자가 제공한 제한에 따라 집합을 반환 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbsch.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)