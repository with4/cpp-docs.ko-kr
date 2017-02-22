---
title: "저장 프로시저 정의 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB, 저장 프로시저"
  - "저장 프로시저, 정의"
  - "저장 프로시저, OLE DB"
  - "저장 프로시저, 구문"
ms.assetid: 54949b81-3275-4dd9-96e4-3eda1ed755f2
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 저장 프로시저 정의
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

저장 프로시저를 호출하기 전에 먼저 [DEFINE\_COMMAND](../../data/oledb/define-command.md) 매크로를 사용하여 저장 프로시저를 정의해야 합니다.  명령을 정의하는 경우 물음표\(?\)를 매개 변수 표식으로 사용하여 매개 변수를 나타냅니다.  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{INSERT {name, phone} into shippers  (?,?)}")  
```  
  
 이 코드 예제에 사용된 구문\(중괄호 등이 사용됨\)은 SQL Server에만 해당된다는 점에 주의하십시오.  저장 프로시저에서 사용하는 구문은 사용하는 공급자에 따라 다를 수 있습니다.  
  
 그 다음, 명령에서의 순서대로 매개 변수가 나열된 매개 변수 맵에서 명령에 사용한 매개 변수를 지정하십시오.  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(1, m_Name)   // name corresponds to first '?' param  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Phone)  // phone corresponds to second '?' param  
END_PARAM_MAP()  
```  
  
 이전 예제에서는 저장 프로시저를 진행되는 대로 정의합니다.  일반적으로 코드를 효과적으로 다시 사용할 수 있도록, 데이터베이스에는 "Sales by Year" 또는 "dt\_adduserobject" 같은 이름을 가진 미리 정의된 저장 프로시저 집합이 있습니다. 사용자는 SQL Server 엔터프라이즈 관리자를 사용하여 이들의 정의를 볼 수 있습니다.  다음과 같이 호출합니다\('?' 매개 변수 배치는 저장 프로시저의 인터페이스에 따라 달라짐\).  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL \"Sales by Year\" (?,?) }")  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL dbo.dt_adduserobject (?,?) }")  
```  
  
 그런 다음 명령 클래스를 선언합니다.  
  
```  
class CMySProc : public CCommand<CAccessor<CMySProcAccessor> >  
```  
  
 마지막으로 다음과 같이 `OpenRowset`에서 저장 프로시저를 호출합니다.  
  
```  
CSession m_session;  
HRESULT OpenRowset()  
{  
   return CCommand<CAccessor<CMySProcAccessor> >::Open(m_session);  
}  
```  
  
 또한 사용자는 다음과 같이 데이터베이스 특성 [db\_command](../../windows/db-command.md)를 사용하여 저장 프로시저를 정의할 수 있다는 점을 참고하십시오.  
  
```  
db_command("{ ? = CALL dbo.dt_adduserobject }")  
```  
  
## 참고 항목  
 [저장 프로시저 사용](../../data/oledb/using-stored-procedures.md)