---
title: "CNoAccessor 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
dev_langs: C++
helpviewer_keywords: CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 799fe151b22748da25901139a5aefe67460b2484
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cnoaccessor-class"></a>CNoAccessor 클래스
템플릿 인수로 사용할 수 있습니다 (`TAccessor`) 템플릿 클래스에 대 한 같은 `CCommand` 및 `CTable`, 접근자 클래스 인수를 필요로 하는 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CNoAccessor  
```  
  
## <a name="remarks"></a>설명  
 사용 하 여 `CNoAccessor` 출력 열 또는 매개 변수를 지원 하도록 클래스 하지 않을 때 템플릿 인수로 합니다.  
  
 `CNoAccessor`다른 클래스 속성에 해당 하는 각각 다음 스텁 메서드를 구현 합니다.  
  
-   **BindColumns** -접근자 열을 바인딩합니다.  
  
-   `BindParameters`-열에 생성된 된 매개 변수를 바인딩합니다.  
  
-   **바인딩할** -바인딩을 만듭니다.  
  
-   **닫기** -접근자를 닫습니다.  
  
-   `ReleaseAccessors`클래스로 만든 접근자를 해제 합니다.  
  
-   `FreeRecordMemory`-해제 해야 하는 현재 레코드의 모든 열을 해제 합니다.  
  
-   `GetColumnInfo`-열린된 행 집합에서 열 정보를 가져옵니다.  
  
-   `GetNumAccessors`클래스로 만든 접근자 수를 검색 합니다.  
  
-   `IsAutoAccessor`-이동 작업 중 접근자에 대 한 데이터를 자동으로 검색 하는 경우 true를 반환 합니다.  
  
-   `GetHAccessor`-지정된 된 접근자의 접근자 핸들을 검색 합니다.  
  
-   `GetBuffer`-책갈피 버퍼에 대 한 포인터를 검색합니다.  
  
-   **NoBindOnNullRowset** -빈 행 집합에 데이터 바인딩 방지 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)