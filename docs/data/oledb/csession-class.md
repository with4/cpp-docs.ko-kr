---
title: "CSession 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSession
- ATL::CSession
- ATL.CSession
dev_langs:
- C++
helpviewer_keywords:
- CSession class
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4a5f2a764aaa7e10b957955dc11ee35ee44f9472
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="csession-class"></a>CSession 클래스
단일 데이터베이스 액세스 세션을 나타냅니다.  
  
## <a name="syntax"></a>구문

```cpp
class CSession  
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[중단](../../data/oledb/csession-abort.md)|취소 (종료) 트랜잭션이 있습니다.|  
|[닫기](../../data/oledb/csession-close.md)|세션을 닫습니다.|  
|[커밋](../../data/oledb/csession-commit.md)|트랜잭션을 커밋합니다.|  
|[GetTransactionInfo](../../data/oledb/csession-gettransactioninfo.md)|트랜잭션에 대 한 정보를 반환 합니다.|  
|[열기](../../data/oledb/csession-open.md)|데이터 원본 개체에 대 한 새 세션을 엽니다.|  
|[StartTransaction](../../data/oledb/csession-starttransaction.md)|이 세션에 대 한 새 트랜잭션을 시작합니다.|  
  
## <a name="remarks"></a>설명  
 하나 이상의 세션으로 표시 된 각 공급자 연결 (데이터 원본)에 연결할 수 있습니다는 [CDataSource](../../data/oledb/cdatasource-class.md) 개체입니다. 새로 만들려면 `CSession` 에 대 한는 `CDataSource`, 호출 [csession:: Open](../../data/oledb/csession-open.md)합니다. 데이터베이스 트랜잭션을 시작 하려면 `CSession` 제공는 `StartTransaction` 메서드. 트랜잭션이 시작 되 면을 사용 하 여 커밋할 수 있습니다는 **커밋** 메서드를 사용 하 여 취소 또는 **중단** 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CatDB](../../visual-cpp-samples.md)   
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)