---
title: "출력 매개 변수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
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
  - "프로시저 호출"
  - "프로시저 호출, 저장 프로시저"
  - "저장 프로시저, 호출"
  - "저장 프로시저, 매개 변수"
ms.assetid: 4f7c2700-1c2d-42f3-8c9f-7e83962b2442
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 출력 매개 변수
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

저장 프로시저를 호출하는 것은 SQL 명령을 호출하는 것과 비슷합니다.  이들의 주된 차이점은 저장 프로시저에서는 출력 매개 변수\(또는 "outparameters"\)와 반환 값을 사용한다는 점입니다.  
  
 다음 저장 프로시저에서 첫 번째 '?'는 반환 값\(phone\)이고 두 번째 '?'는 입력 매개 변수\(name\)입니다.  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }")  
```  
  
 매개 변수 맵에서 입력과 출력 매개 변수를 지정합니다.  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)  
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter  
END_PARAM_MAP()  
```  
  
 응용 프로그램은 저장 프로시저에서 반환된 출력을 처리해야 합니다.  다른 OLE DB 공급자는 결과를 처리하는 동안 서로 다른 시기에 출력 매개 변수와 반환 값을 반환합니다.  예를 들어, SQL Server용 Microsoft OLE DB 공급자\(SQLOLEDB\)는 저장 프로시저에서 반환된 결과 집합을 소비자가 검색 또는 취소할 때까지 출력 매개 변수와 반환 코드를 제공하지 않습니다.  출력은 서버로부터 마지막 TDS 패킷에 반환됩니다.  
  
## 행 개수  
 OLE DB 소비자 템플릿을 사용하여 outparameter가 있는 저장 프로시저를 실행하는 경우, 사용자가 행 집합을 닫아야만 행 개수가 설정됩니다.  
  
 예를 들어, 다음과 같이 행 집합과 outparameter가 있는 저장 프로시저의 경우를 살펴봅시다.  
  
```  
create procedure sp_test  
   @_rowcount integer output  
as  
   select top 50 * from test  
   @_rowcount = @@rowcount  
return 0  
```  
  
 @\_rowcount outparameter는 테스트 테이블에서 실제로 반환된 행의 수를 보고합니다.  그러나 이 저장 프로시저는 행의 수를 최대 50으로 제한합니다.  따라서 테스트에 100개의 행이 있는 경우, 이 코드는 상위 50개의 행만 검색하므로 rowcount는 50이 됩니다.  테이블에 30개의 행만 있는 경우, rowcount는 30이 됩니다.  **Close** 또는 **CloseAll**을 호출하여 값을 페치하기 전에 outparameter를 채워야 합니다.  
  
## 참고 항목  
 [저장 프로시저 사용](../../data/oledb/using-stored-procedures.md)