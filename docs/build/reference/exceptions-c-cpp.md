---
title: "예외(C/C++) | Microsoft Docs"
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
  - "ERROR_MOD_NOT_FOUND"
  - "vcppException"
  - "ERROR_SEVERITY_ERROR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ 예외 처리, 지연 DLL 로드"
  - "지연 DLL 로드, 예외"
  - "ERROR_MOD_NOT_FOUND 예외"
  - "ERROR_SEVERITY_ERROR 예외"
  - "vcppException"
ms.assetid: c03be05d-1c39-4f35-84cf-00c9af3bae9a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 예외(C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

오류가 발생하면 다음과 같은 두 가지 예외 코드가 발생할 수 있습니다.  
  
-   **LoadLibrary** 오류에 대한 예외 코드  
  
-   **GetProcAddress** 오류에 대한 예외 코드  
  
 다음은 예외 정보입니다.  
  
```  
//  
// Exception information  
//  
#define FACILITY_VISUALCPP  ((LONG)0x6d)  
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)  
```  
  
 throw되는 예외 코드는 표준 VcppException\(ERROR\_SEVERITY\_ERROR, ERROR\_MOD\_NOT\_FOUND\) 및 VcppException\(ERROR\_SEVERITY\_ERROR, ERROR\_PROC\_NOT\_FOUND\) 값입니다.  이 예외는 포인터를 LPDWORD 값의 형식으로 **DelayLoadInfo** 구조체에 전달합니다. 이 값은 [EXCEPTION\_RECORD](http://msdn.microsoft.com/library/windows/desktop/aa363082) 구조체의 ExceptionInformation\[0\] 필드에서 **GetExceptionInformation**으로 검색할 수 있습니다.  
  
 또한 grAttrs 필드의 비트가 잘못 설정된 경우 ERROR\_INVALID\_PARAMETER 예외가 throw됩니다.  이 예외는 치명적입니다.  
  
 자세한 내용은 [구조체 및 상수 정의](../../build/reference/structure-and-constant-definitions.md)를 참조하십시오.  
  
## 참고 항목  
 [오류 처리 및 알림](../../build/reference/error-handling-and-notification.md)