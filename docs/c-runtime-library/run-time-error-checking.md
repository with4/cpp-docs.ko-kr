---
title: "런타임 오류 검사 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.runtime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "런타임 오류 검사"
  - "런타임 오류, 확인"
ms.assetid: c965dd01-57ad-4a3c-b1d6-5aa04f920501
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 런타임 오류 검사
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C 런타임 라이브러리는 런타임 오류 검사\(RTC\)를 지원하는 함수를 포함합니다.  런타임 오류 검사는 특정 유형의 런타임 오류가 보고 되는 프로그램을 작성할 수 있습니다.  오류가 보고 되는 방법과 어떤 종류의 오류를 보고되는지를 지정합니다.  자세한 내용은 [런타임 오류 검사](../Topic/How%20to:%20Use%20Native%20Run-Time%20Checks.md)를 참조하십시오.  
  
 런타임 오류 검사하는 방식을 사용자 지정 하려면 다음과 같은 함수를 사용합니다.  
  
### 런타임 오류 검사를 사용합니다.  
  
|Function|기능|해당 .NET Framework|  
|--------------|--------|-----------------------|  
|[\_RTC\_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md)|런타임 오류 검사 형식에 대한 간단한 설명을 반환합니다.||  
|[\_RTC\_NumErrors](../c-runtime-library/reference/rtc-numerrors.md)|런타임 오류 검사에서 발견된 오류 형식의 수를 반환합니다.||  
|[\_RTC\_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md)|런타임 오류 검사의 보고에 대한 처리기 함수를 지정합니다.||  
|[\_RTC\_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md)|형식을 사용한 런타임 오류 검사로 발견된 오류를 연관시킵니다.||  
  
## 참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)   
 [\/RTC\(런타임 오류 검사\)](../build/reference/rtc-run-time-error-checks.md)   
 [runtime\_checks](../preprocessor/runtime-checks.md)   
 [RTC sample](http://msdn.microsoft.com/ko-kr/b3415b09-f6fd-43dc-8c02-9a910bc2574e)   
 [디버그 루틴](../c-runtime-library/debug-routines.md)