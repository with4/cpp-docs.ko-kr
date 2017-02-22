---
title: "SET_PARAM_TYPE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SET_PARAM_TYPE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SET_PARAM_TYPE 매크로"
ms.assetid: 85979070-2d55-4c67-94b1-9b9058babc59
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# SET_PARAM_TYPE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`SET_PARAM_TYPE` 매크로 입력, 출력 또는 입력\/출력 다음에 오는 `COLUMN_ENTRY` 매크로를 지정합니다.  
  
## 구문  
  
```  
  
SET_PARAM_TYPE(  
type  
 )  
  
```  
  
#### 매개 변수  
 `type`  
 \[in\] 매개 변수에 대해 설정할 형식입니다.  
  
## 설명  
 공급자는 기본 데이터 소스에서 지원되는 매개 변수 입력\/출력 형식만 지원합니다. 형식은 하나 이상의 **DBPARAMIO** 값 조합입니다\(*OLE DB 프로그래머 참조*에서 [DBBINDING 구조체](https://msdn.microsoft.com/en-us/library/ms716845.aspx) 참조\).  
  
-   **DBPARAMIO\_NOTPARAM** 이 접근자에는 매개 변수가 없습니다. 일반적으로 사용자에게 매개 변수가 무시됨을 알리기 위해 행 접근자에서 **eParamIO**를 이 값으로 설정합니다.  
  
-   **DBPARAMIO\_INPUT** 입력 매개 변수입니다.  
  
-   **DBPARAMIO\_OUTPUT** 출력 매개 변수입니다.  
  
-   **DBPARAMIO\_INPUT &#124; DBPARAMIO\_OUTPUT** 입력 및 출력 매개 변수입니다.  
  
## 예제  
 [!CODE [NVC_OLEDB_Consumer#18](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#18)]  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)