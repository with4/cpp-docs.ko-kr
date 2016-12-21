---
title: "오류 처리(CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.errors"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "오류 처리, C 루틴"
  - "오류 처리, 라이브러리 루틴"
  - "논리 오류"
  - "테스트, 프로그램 오류"
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 오류 처리(CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로그램 오류를 처리 하려면 이 루틴을 사용 합니다.  
  
### 오류 처리 루틴  
  
|루틴|기능|해당 .NET Framework|  
|--------|--------|-----------------------|  
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) 매크로|런타임 라이브러리의 디버그 및 릴리스 버전에서 사용할 수 있는 프로그래밍 논리 오류에 대한 테스트입니다.|[\<caps:sentence id\="tgt8" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug:: 어설션\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[\_ASSERT, \_ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) 매크로|`assert` 와 유사하지만, 런타임 라이브러리의 디버그 버전에서만 사용할 수 있습니다.|[\<caps:sentence id\="tgt11" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug:: 어설션\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[clearerr](../c-runtime-library/reference/clearerr.md)|오류 지시자를 다시 설정 합니다.  `rewind` 를 호출하거나 스트림을 닫는 것은 또한 오류 지시자를 재설정 합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_eof](../c-runtime-library/reference/eof.md)|하위 수준 I\/O에서 파일의 끝에 대한 검사|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[feof](../c-runtime-library/reference/feof.md)|파일의 끝에 대한 테스트입니다.  `_read`  가 0을 반환할 때 또한 파일의 끝은 표시 됩니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[ferror](../c-runtime-library/reference/ferror.md)|스트림 I\/O 오류에 대한 테스트|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_RPT, \_RPTF](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) 매크로|런타임 라이브러리의 디버그 버전에서만 사용할 수 있는 `printf` 와 유사한 보고서를 생성합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[\_set\_error\_mode](../c-runtime-library/reference/set-error-mode.md)|C 런타임이 가능한 프로그램을 종료합니다. 오류에 대한 오류 메시지를 기록합니다. 기본 위치가 아닌 위치를 결정하기 위해 `__error_mode`를 수정합니다.||  
|[\_set\_purecall\_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|순수 가상 함수 호출에 대한 처리기를 설정합니다.||  
  
## 참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)