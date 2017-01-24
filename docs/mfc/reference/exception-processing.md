---
title: "예외 처리 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.exceptions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO(Data Access Objects), 예외"
  - "예외 매크로"
  - "예외, MFC throw 함수"
  - "예외, 처리"
  - "매크로, 예외 처리"
  - "MFC, 예외"
  - "OLE 예외, MFC 함수"
  - "종료 함수, MFC"
ms.assetid: 26d4457c-8350-48f5-916e-78f919787c30
caps.latest.revision: 16
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 예외 처리
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로그램이 실행 될 때 여러 비정상적인 상태 및 "예외" 라는 오류가 발생할 수 있습니다.  이러한 메모리, 리소스 할당 오류 및 오류 파일을 찾을 수의 부족을 포함할 수 있습니다.  
  
 Microsoft 기반 클래스 라이브러리는 c \+ \+ ANSI 표준 위원회에서 제안한 후 밀접하게 모델링된 예외 처리 체계를 사용합니다.  비정상적인 상황이 발생할 수 있는 함수를 호출 하기 전에 예외 처리기를 설정 해야 합니다.  함수는 비정상 상태를 발견하는 경우 예외를 throw 하고 예외 처리기로 제어가 전달됩니다.  
  
 Microsoft Foundation 클래스 라이브러리에 포함된 여러 매크로는 예외 처리기를 설정합니다.  필요한 경우, 여러 다른 전역 함수는 특수한 예외를 throw 하고 프로그램을 종료하는데 도움을 청합니다.  이러한 매크로 및 전역 함수는 다음 범주로 구분됩니다.  
  
-   [예외 매크로](#_mfc_exception_macros)는 예외 처리기를 구성합니다.  
  
-   [예외를 throw 하는 함수](#_mfc_exception.2d.throwing_functions)는 특정 형식의 예외를 생성합니다.  
  
-   [종료 함수](#_mfc_termination_functions)는 프로그램 종료의 원인이 있습니다.  
  
 예제 및 자세한 내용을 보려면  [예외](../../mfc/exception-handling-in-mfc.md)을 참고하십시오.  
  
### 예외 매크로  
  
|||  
|-|-|  
|[Try](../Topic/TRY.md)|예외 처리 코드 블록을 지정합니다.|  
|[CATCH](../Topic/CATCH.md)|**시도** 블록 앞에서 예외를 catch 하는 코드 블록을 지정합니다.|  
|[CATCH\_ALL](../Topic/CATCH_ALL.md)|**시도** 블록 앞에서 모든 예외를 catch 하는 코드 블록을 지정합니다.|  
|[AND\_CATCH](../Topic/AND_CATCH.md)|**시도** 블록 앞에서 추가적인 예외 형식을 catch 하는 코드 블록을 지정합니다.|  
|[AND\_CATCH\_ALL](../Topic/AND_CATCH_ALL.md)|**시도** 블록 앞에서 thorw된 다른 모든 추가 예외를  catch 할 것인지에 대한 코드 블록을 지정합니다.|  
|[END\_CATCH](../Topic/END_CATCH.md)|**CATCH** 또는  `AND_CATCH`  코드 블록으로 끝냅니다.|  
|[END\_CATCH\_ALL](../Topic/END_CATCH_ALL.md)|`CATCH_ALL`  코드 블록으로 끝냅니다.|  
|[THROW](../Topic/THROW%20\(MFC\).md)|지정된 예외를 throw합니다.|  
|[THROW\_LAST](../Topic/THROW_LAST.md)|다음 외부 처리기에 현재 처리된 예외가 throw 됩니다.|  
  
### 예외 throw 함수  
  
|||  
|-|-|  
|[AfxThrowArchiveException](../Topic/AfxThrowArchiveException.md)|아카이브 예외가 throw 됩니다.|  
|[AfxThrowFileException](../Topic/AfxThrowFileException.md)|파일 예외를 throw합니다.|  
|[AfxThrowMemoryException](../Topic/AfxThrowMemoryException.md)|메모리 예외를 throw합니다.|  
|[AfxThrowNotSupportedException](../Topic/AfxThrowNotSupportedException.md)|지원되지 않는 예외를 throw합니다.|  
|[AfxThrowResourceException](../Topic/AfxThrowResourceException.md)|Windows 리소스가 아닌 예외를 throw합니다.|  
|[AfxThrowUserException](../Topic/AfxThrowUserException.md)|프로그램이 사용자가 시작한 작업에서 예외를 throw 합니다.|  
  
 MFC는 OLE 예외에 대해 구체적으로 예외를 throw 하는 두 가지 기능을 제공합니다.  
  
### OLE 예외 함수  
  
|||  
|-|-|  
|[AfxThrowOleDispatchException](../Topic/AfxThrowOleDispatchException.md)|OLE 자동화 함수 내에서 예외를 throw합니다.|  
|[AfxThrowOleException](../Topic/AfxThrowOleException.md)|OLE 예외를 throw합니다.|  
  
 데이터베이스 예외를 지원하기 위해 데이터베이스 클래스는 두 가지 예외 클래스를 제공합니다,  `CDBException`  및  `CDaoException` , 그리고 예외 형식을 지원 하도록 전역 함수또한 지원합니다:  
  
### DAO 예외 함수  
  
|||  
|-|-|  
|[AfxThrowDaoException](../Topic/AfxThrowDaoException.md)|코드에서 [CDaoException](../../mfc/reference/cdaoexception-class.md) 을 thorow합니다.|  
|[AfxThrowDBException](../Topic/AfxThrowDBException.md)|코드에서 [CDBException](../../mfc/reference/cdbexception-class.md) 을 thorow합니다.|  
  
 MFC에서는 다음 종료 함수를 제공합니다.  
  
### 종료 함수  
  
|||  
|-|-|  
|[AfxAbort](../Topic/AfxAbort.md)|치명적인 오류가 발생 하는 경우 응용 프로그램 종료를 호출합니다.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)   
 [CException Class](../../mfc/reference/cexception-class.md)