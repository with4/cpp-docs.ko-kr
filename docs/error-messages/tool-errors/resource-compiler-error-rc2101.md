---
title: "리소스 컴파일러 오류 RC2101 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC2101"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2101"
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 리소스 컴파일러 오류 RC2101
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

전처리 RC 파일에서 지시문이 잘못되었습니다.  
  
 리소스 컴파일러 파일에 **\#pragma** 지시문이 들어 있습니다.  
  
 포함 파일을 처리할 때 리소스 컴파일러가 정의하는 RC\_INVOKED 상수와 함께 **\#ifndef** 전처리기 지시문을 사용하십시오.  RC\_INVOKED 상수가 정의될 때 처리되지 않는 코드 블록 내부에 **\#pragma** 지시문을 배치하십시오.  블록의 코드는 리소스 컴파일러가 아닌 C\/C\+\+ 컴파일러에 의해서만 처리됩니다.  다음 샘플 코드는 이 기술을 보여 줍니다.  
  
```  
#ifndef RC_INVOKED  
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler  
#endif  
```  
  
 .RC 파일에서는 **\#pragma** 전처리기 지시문이 아무런 의미가 없습니다.   **\#include** 전처리기 지시문은 헤더 파일\(프로젝트 기반 사용자 지정 헤더 파일이나 Microsoft에서 제품과 함께 제공한 표준 헤더 파일\)을 포함하기 위해 .RC 파일에서 주로 사용됩니다.  이러한 포함 파일 중 일부에는 **\#pragma** 지시문이 들어 있습니다.  헤더 파일 한 개에 여러 헤더 파일을 포함할 수 있으므로 잘못된 **\#pragma** 지시문이 들어 있는 파일을 즉시 알아낼 수는 없습니다.  
  
 **\#ifndef** RC\_INVOKED 기술을 통해 프로젝트 기반 헤더 파일에 헤더 파일을 포함하는 작업을 제어할 수 있습니다.