---
title: 'Ccommand:: Close | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CCommand.Close
- CCommand::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 4da9c02c-7082-4e47-a0fa-78b546f0f7d2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 10d3ce633add0dea4a3b9a79a32fd380761b5a2f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="ccommandclose"></a>CCommand::Close
명령과 연결 된 접근자 행 집합을 해제 합니다.  
  
## <a name="syntax"></a>구문

```cpp
void Close();  
```  
  
## <a name="remarks"></a>설명  
 명령은 행 집합, 결과 집합 접근자 및 (옵션) (테이블과 달리, 매개 변수를 지원 하지 않는 매개 변수 접근자를 불필요 하며) 매개 변수 접근자를 사용 합니다.  
  
 둘 다를 호출 해야 명령을 실행할 때 `Close` 및 [ReleaseCommand](../../data/oledb/ccommand-releasecommand.md) 명령 실행 후 합니다.  
  
 호출 하 여 각 결과 집합 접근자를 해제 해야 반복 해 서 동일한 명령을 실행 하려는 경우 `Close` 호출 하기 전에 `Execute`합니다. 계열의 끝에 호출 하 여 매개 변수 접근자를 해제 해야 `ReleaseCommand`합니다. 출력 매개 변수가 있는 저장된 프로시저를 호출 하는 또 다른 일반적인 시나리오입니다. 대부분의 공급자 (예: SQL Server 용 OLE DB 공급자)에 출력 매개 변수 값은 액세스할 수 없습니다 결과 set 접근자를 닫을 때까지. 호출 `Close` 반환 된 행 집합 및 결과 집합 접근자 있지만 하지 매개 변수 접근자를 닫으려면 수 있도록 출력 매개 변수 값을 검색할 수 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 호출 하는 방법을 보여 줍니다. `Close` 및 `ReleaseCommand` 반복 해 서 동일한 명령을 실행할 때.  
  
 [!code-cpp[NVC_OLEDB_Consumer#2](../../data/oledb/codesnippet/cpp/ccommand-close_1.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CCommand 클래스](../../data/oledb/ccommand-class.md)   
 [CCommand::ReleaseCommand](../../data/oledb/ccommand-releasecommand.md)