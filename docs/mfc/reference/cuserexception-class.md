---
title: "CUserException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CUserException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUserException class"
  - "오류[C++], 잡기"
  - "예외, throw"
  - "operations [C++]"
  - "operations [C++], 중지"
  - "예외 throw, stopping user operations"
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CUserException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

최종 사용자 작업을 중지 하려면 발생 합니다.  
  
## 구문  
  
```  
class CUserException : public CSimpleException  
```  
  
## 설명  
 사용 `CUserException` 에 대 한 응용 프로그램별 예외 throw\/catch 예외 메커니즘을 사용 하려면. 이때   클래스 이름에 "사용자"내 사용자에 게 예외를 처리 해야 하는 것 처럼."해석 될 수 있습니다.  
  
 A `CUserException` 일반적으로 전역 함수를 호출 하면 throw 됩니다 `AfxMessageBox` 작업에 실패 한 사용자에 게 알리려면.  예외 처리기를 작성 하는 경우 특수 사용자가 일반적으로 이미 실패를 알렸습니다 하므로 예외를 처리 합니다.  프레임 워크에 따라서는이 예외를 throw 합니다.  Throw 하는 `CUserException` 직접 사용자 경고 및 다음 전역 함수 호출 `AfxThrowUserException`.  
  
 아래 예제에서는 실패할 수 있습니다 운영을 포함 하는 함수 경고 메시지를 표시 하 고 throw 된 `CUserException`.  호출 하는 함수는 예외를 catch 하 고 특수 하 게 처리:  
  
 [!code-cpp[NVC_MFCExceptions#24](../../mfc/codesnippet/CPP/cuserexception-class_1.cpp)]  
  
 사용에 대 한 자세한 내용은 `CUserException`, 문서를 참조 하십시오.  [예외 처리 \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [넓습니다](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CUserException`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CException Class](../../mfc/reference/cexception-class.md)   
 [AfxMessageBox](../Topic/AfxMessageBox.md)   
 [AfxThrowUserException](../Topic/AfxThrowUserException.md)   
 [어떻게 i: 만들지 나만의 사용자 지정 예외 클래스?](http://go.microsoft.com/fwlink/?LinkId=128045)