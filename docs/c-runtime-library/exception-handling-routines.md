---
title: "예외 처리 루틴 | Microsoft Docs"
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
  - "c.exceptions"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "예외 처리, 루틴"
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 예외 처리 루틴
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C \+ \+ 예외 처리 함수를 사용하여 프로그램 실행 중에 예기치 않은 상황 으로부터 복구합니다.  
  
### 예외 처리 함수  
  
|Function|기능|해당 .NET Framework|  
|--------------|--------|-----------------------|  
|[\_set\_se\_translator](../c-runtime-library/reference/set-se-translator.md)|C\+\+ 예외 형식 같은 Win32 예외 처리 \(C 구조적 예외\)|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[set\_terminate](../c-runtime-library/reference/set-terminate-crt.md)|`terminate` 에게 호출되기 위해 종료 루틴을 설치합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[set\_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|`unexpected`가 호출한 자체 종료 함수를 설치합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[terminate](../c-runtime-library/reference/terminate-crt.md)|후에 호출 자동으로 특정 상황에서 예외가 throw 됩니다.  이 `terminate` 함수는 `abort` 또는 `set_terminate` 을 사용하여 지정한 함수를 호출합니다.|해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.|  
|[unexpected](../c-runtime-library/reference/unexpected-crt.md)|`terminate` 또는 `set_unexpected`를 사용하여 사용자가 지정한 함수를 호출하세요.  이 `unexpected` 함수는 현재 Microsoft c \+ \+ 예외 처리 구현에 사용 되지 않습니다|[\<caps:sentence id\="tgt30" sentenceid\="ec8332f3bf55c7bd183338eca87744ec" class\="tgtSentence"\>System::Exception Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.exception.aspx)|  
  
## 참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)