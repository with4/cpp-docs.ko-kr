---
title: "CFileException Class | Microsoft Docs"
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
  - "CFileException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFile class, exceptions of"
  - "CFileException class"
  - "예외, file type"
ms.assetid: f6491bb9-bfbc-42fd-a952-b33f9b62323f
caps.latest.revision: 20
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFileException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일 관련 예외 조건을 나타냅니다.  
  
## 구문  
  
```  
class CFileException : public CException  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CFileException::CFileException](../Topic/CFileException::CFileException.md)|`CFileException` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CFileException::ErrnoToException](../Topic/CFileException::ErrnoToException.md)|반환 코드는 런타임 오류 번호에 해당 발생 합니다.|  
|[CFileException::GetErrorMessage](../Topic/CFileException::GetErrorMessage.md)|예외를 설명 하는 메시지를 검색 합니다.|  
|[CFileException::OsErrorToException](../Topic/CFileException::OsErrorToException.md)|운영 체제 오류 코드에 해당 하는 원인 코드를 반환 합니다.|  
|[CFileException::ThrowErrno](../Topic/CFileException::ThrowErrno.md)|런타임 오류 번호에 따라 파일 예외를 throw 합니다.|  
|[CFileException::ThrowOsError](../Topic/CFileException::ThrowOsError.md)|운영 체제 오류 번호에 따라 파일 예외를 throw 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CFileException::m\_cause](../Topic/CFileException::m_cause.md)|예외 원인에 해당 하는 이식 가능한 코드를 포함 합니다.|  
|[CFileException::m\_lOsError](../Topic/CFileException::m_lOsError.md)|관련된 운영 체제 오류 번호가 들어 있습니다.|  
|[CFileException::m\_strFileName](../Topic/CFileException::m_strFileName.md)|이 예외에 대 한 파일 이름을 포함합니다.|  
  
## 설명  
 `CFileException` 클래스 휴대용 원인 코드와 운영 체제 특정 오류 번호를 포함 하는 공용 데이터 멤버를 포함 합니다.  클래스는 정적 멤버 함수가 파일 예외를 throw 하 고 반환 코드는 C 런타임 오류와 작동 시스템 오류 발생을 제공 합니다.  
  
 `CFileException`개체를 생성 하 고 발생 `CFile` 멤버 함수에서 파생 된 클래스의 멤버 함수입니다.  이러한 개체의 범위 내에서 액세스할 수 있는  **CATCH** 식.  이식성에 대해 원인 코드 예외 사유를 얻을 수 있음.  예외에 대 한 자세한 내용은  [예외 처리 \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [넓습니다](../../mfc/reference/cexception-class.md)  
  
 `CFileException`  
  
## 요구 사항  
 **헤더:**  afx.h  
  
## 참고 항목  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [예외 처리](../../mfc/reference/exception-processing.md)