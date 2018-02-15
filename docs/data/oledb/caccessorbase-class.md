---
title: "CAccessorBase 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CAccessorBase
dev_langs:
- C++
helpviewer_keywords:
- CAccessorBase class
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0f57c771f0d129683bde0629f9c28cfbaa897ee4
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="caccessorbase-class"></a>CAccessorBase 클래스
OLE DB 템플릿의 모든 접근자가이 클래스에서 파생 됩니다. `CAccessorBase` 여러 접근자를 관리 하는 하나의 행 집합을 허용 합니다. 또한 매개 변수 및 출력 열 모두에 대 한 바인딩을 제공합니다.  
  
## <a name="syntax"></a>구문

```cpp
// Replace with syntax  
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[닫기](../../data/oledb/caccessorbase-close.md)|접근자를 닫습니다.|  
|[GetHAccessor](../../data/oledb/caccessorbase-gethaccessor.md)|접근자 핸들을 검색 합니다.|  
|[GetNumAccessors](../../data/oledb/caccessorbase-getnumaccessors.md)|클래스로 만든 접근자 수를 검색 합니다.|  
|[IsAutoAccessor](../../data/oledb/caccessorbase-isautoaccessor.md)|지정 된 접근자 자동 인지 테스트 합니다.|  
|[ReleaseAccessors](../../data/oledb/caccessorbase-releaseaccessors.md)|접근자를 해제합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)