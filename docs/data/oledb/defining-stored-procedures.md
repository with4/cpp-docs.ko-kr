---
title: "저장된 프로시저 정의 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- stored procedures, syntax
- OLE DB, stored procedures
- stored procedures, defining
- stored procedures, OLE DB
ms.assetid: 54949b81-3275-4dd9-96e4-3eda1ed755f2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3262396bcaafd1522278d0ac53be5d715966b9d2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="defining-stored-procedures"></a>저장 프로시저 정의
저장된 프로시저를 호출 하기 전에 먼저 정의 해야를 사용 하 여 [DEFINE_COMMAND](../../data/oledb/define-command.md) 매크로입니다. 명령을 정의 하는 경우 매개 변수 표식으로 물음표 (?) 매개 변수를 나타냅니다.  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{INSERT {name, phone} into shippers  (?,?)}")  
```  
  
 이 항목의 코드 예제에 사용 되는 구문 (중괄호 등에 사용)은 SQL Server에만 확인 합니다. 저장된 프로시저에서 사용 하는 구문을 사용 하는 공급자에 따라 달라질 수 있습니다.  
  
 다음으로 매개 변수 맵의 매개 변수는 명령에서 발생 하는 순서로 나열 하는 명령에서 사용 매개 변수를 지정 합니다.  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(1, m_Name)   // name corresponds to first '?' param  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Phone)  // phone corresponds to second '?' param  
END_PARAM_MAP()  
```  
  
 되는 것 만큼 앞의 예제는 저장된 프로시저를 정의 합니다. 일반적으로 코드의 효율적인 재사용에 대 한 데이터베이스 집합이 포함 되어 "Year Sales" 또는 "dt_adduserobject" 같은 이름 가진 미리 정의 된 저장된 프로시저 SQL Server 엔터프라이즈 관리자를 사용 하 여 해당 정의 볼 수 있습니다. 다음과 같이 호출 (위치는 '?' 매개 변수는 저장된 프로시저의 인터페이스에 따라 다릅니다):  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL \"Sales by Year\" (?,?) }")  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL dbo.dt_adduserobject (?,?) }")  
```  
  
 그런 다음 명령 클래스를 선언 합니다.  
  
```  
class CMySProc : public CCommand<CAccessor<CMySProcAccessor>>  
```  
  
 마지막으로 저장된 프로시저 호출 `OpenRowset` 다음과 같습니다.  
  
```  
CSession m_session;  

HRESULT OpenRowset()  
{  
   return CCommand<CAccessor<CMySProcAccessor>>::Open(m_session);  
}  
```  
  
 또한 데이터베이스에서 특성을 사용 하 여 저장된 프로시저를 정의할 수 참고 [db_command](../../windows/db-command.md) 다음과 같습니다.  
  
```  
db_command("{ ? = CALL dbo.dt_adduserobject }")  
```  
  
## <a name="see-also"></a>참고 항목  
 [저장 프로시저 사용](../../data/oledb/using-stored-procedures.md)