---
title: "check_stack | Microsoft Docs"
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
  - "vc-pragma.check_stack"
  - "check_stack_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "check_stack pragma"
  - "pragma, check_stack"
  - "pragma, check_stack 사용 현황 테이블"
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# check_stack
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**off**\(또는 **–**\)를 지정한 경우 스택 프로브를 해제하고, **on**\(또는 **\+**\)을 지정한 경우 스택 프로브를 설정하도록 컴파일러에 지시합니다.  
  
## 구문  
  
```  
  
      #pragma check_stack([ {on | off}] )  
#pragma check_stack{+ | –}  
```  
  
## 설명  
 인수를 지정하지 않으면 스택 프로브가 기본값에 따라 처리됩니다.  이 pragma는 pragma가 표시된 후 정의된 첫 번째 함수에서 적용됩니다.  스택 프로브는 인라인으로 생성된 함수의 일부나 매크로의 일부가 아닙니다.  
  
 **check\_stack** pragma에 대한 인수를 지정하지 않는 경우 스택 검사는 명령줄에 지정된 동작으로 되돌아갑니다.  자세한 내용은 [컴파일러 참조](../build/reference/compiler-options.md)를 참조하십시오.  **\#pragma check\_stack** 및 [\/Gs](../build/reference/gs-control-stack-checking-calls.md) 옵션의 상호 작용이 다음 표에 요약되어 있습니다.  
  
### check\_stack Pragma 사용  
  
|구문|\/Gs 옵션을 사용한<br /><br /> 컴파일 여부|작업|  
|--------|-----------------------------|--------|  
|**\#pragma check\_stack\( \)** 또는<br /><br /> **\#pragma check\_stack**|예|뒤에 오는 함수에 대한 스택 검사 해제|  
|**\#pragma check\_stack\( \)** 또는<br /><br /> **\#pragma check\_stack**|아니요|뒤에 오는 함수에 대한 스택 검사 설정|  
|**\#pragma check\_stack\(on\)**<br /><br /> 또는 **\#pragma check\_stack \+**|예 또는 아니요|뒤에 오는 함수에 대한 스택 검사 설정|  
|**\#pragma check\_stack\(off\)**<br /><br /> 또는 **\#pragma check\_stack –**|예 또는 아니요|뒤에 오는 함수에 대한 스택 검사 해제|  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)