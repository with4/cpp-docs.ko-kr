---
title: "CInternetException Class | Microsoft Docs"
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
  - "CInternetException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInternetException class"
  - "예외 처리, Internet operations"
  - "예외, 인터넷"
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
caps.latest.revision: 22
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CInternetException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인터넷 작업에 관련 된 예외 조건을 나타냅니다.  
  
## 구문  
  
```  
class CInternetException : public CException  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CInternetException::CInternetException](../Topic/CInternetException::CInternetException.md)|`CInternetException` 개체를 생성합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CInternetException::m\_dwContext](../Topic/CInternetException::m_dwContext.md)|예외를 발생 시킨 작업과 관련 된 컨텍스트 값입니다.|  
|[CInternetException::m\_dwError](../Topic/CInternetException::m_dwError.md)|예외가 발생 하는 오류입니다.|  
  
## 설명  
 `CInternetException` 클래스 두 공용 데이터 멤버를 포함 합니다: 하나 보유 예외와 관련 된 오류 코드 및 다른 오류와 관련 된 인터넷 응용 프로그램의 컨텍스트 식별자를 포함 합니다.  
  
 인터넷 응용 프로그램에 대 한 컨텍스트 식별자에 대 한 자세한 내용은  [WinInet 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [넓습니다](../../mfc/reference/cexception-class.md)  
  
 `CInternetException`  
  
## 요구 사항  
 **헤더:**  afxinet.h  
  
## 참고 항목  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CException Class](../../mfc/reference/cexception-class.md)