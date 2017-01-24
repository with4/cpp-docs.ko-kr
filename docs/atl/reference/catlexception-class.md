---
title: "CAtlException Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAtlException"
  - "ATL::CAtlException"
  - "ATL.CAtlException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlException class"
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 ATL 예외를 정의합니다.  
  
## 구문  
  
```  
  
class CAtlException  
  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CAtlException::CAtlException](../Topic/CAtlException::CAtlException.md)|생성자입니다.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[CAtlException::operator HRESULT](../Topic/CAtlException::operator%20HRESULT.md)|HRESULT 값에 현재 개체를 캐스팅합니다.|  
  
### 공용 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CAtlException::m\_hr](../Topic/CAtlException::m_hr.md)|HRESULT 개체에서 생성 한 오류 상태를 저장 하는 데 사용 된 형식의 변수입니다.|  
  
## 설명  
 A `CAtlException` 개체는 ATL 작업과 관련 된 예외 조건을 나타냅니다.  `CAtlException` 클래스는 예외와 HRESULT 처럼 예외를 처리할 수 있도록 하는 캐스트 연산자에 대 한 이유를 나타내는 상태 코드를 저장 하는 공용 데이터 멤버를 포함 합니다.  
  
 일반적으로 호출을 받을 수 `AtlThrow` 만들기 보다는 `CAtlException` 직접 개체입니다.  
  
## 요구 사항  
 **헤더:** atlexcept.h  
  
## 참고 항목  
 [AtlThrow](../Topic/AtlThrow.md)   
 [Class Overview](../../atl/atl-class-overview.md)