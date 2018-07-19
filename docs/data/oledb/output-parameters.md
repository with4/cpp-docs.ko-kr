---
title: 출력 매개 변수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, calling
- stored procedures, parameters
- procedure calls
- procedure calls, stored procedures
ms.assetid: 4f7c2700-1c2d-42f3-8c9f-7e83962b2442
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8733b967ddab7e6f68fcbee1c80e78500a679f96
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104388"
---
# <a name="output-parameters"></a>출력 매개 변수
저장된 프로시저를 호출 하는 것은 SQL 명령을 호출 하는 것과 비슷합니다. 주요 차이점에는 저장된 프로시저 출력 매개 변수 (또는 "outparameter")를 사용 및 반환 값은입니다.  
  
 다음 저장 프로시저를 첫 번째 '? '입니다. 반환 값 (phone) 및 두 번째'?'는 입력 매개 변수 (이름):  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }")  
```  
  
 매개 변수 맵의 입력 및 출력 매개 변수를 지정합니다.  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)  
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter  
END_PARAM_MAP()  
```  
  
 응용 프로그램이 저장된 프로시저에서 반환 되는 출력을 처리 해야 합니다. 다른 OLE DB 공급자는 출력 매개 변수를 반환 하 고 결과 처리 하는 동안 서로 다른 시간에 값을 반환 합니다. 예를 들어 Microsoft OLE DB 공급자 SQL Server (SQLOLEDB)에 대 한 않습니다 하지 출력 매개 변수를 제공 및 소비자가 검색 또는 저장된 프로시저에서 반환 된 결과 집합을 취소 한 후 반환 될 때까지 코드입니다. 출력은 서버에서 보내는 마지막 TDS 패킷에서 반환 됩니다.  
  
## <a name="row-count"></a>행 개수  
 OLE DB 소비자 템플릿을 사용 하 여 outparameter가 저장된 프로시저를 실행 하는 행 집합을 닫을 때까지 행 수 설정 되지 않았습니다.  
  
 예를 들어 행 집합 및는 outparameter 있는 저장된 프로시저:  
  
```  
create procedure sp_test  
   @_rowcount integer output  
as  
   select top 50 * from test  
   @_rowcount = @@rowcount  
return 0  
```  
  
 @_rowcount outparameter 테스트 테이블에서 실제로 반환 된 행 수를 보고 합니다. 그러나이 저장된 프로시저는 최대 50 행 수를 제한합니다. 예를 들어 테스트에 100 개의 행이 있는 경우 행 개수가 것 50 (하기 때문에이 코드는 상위 50 행만 검색)입니다. 테이블에 30 개 행만 있었습니다 하는 경우 행 개수가 30입니다. 호출 해야 **닫기** 또는 **CloseAll** 해당 값을 인출 하기 전에 outparameter를 채우는 데 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [저장 프로시저 사용](../../data/oledb/using-stored-procedures.md)