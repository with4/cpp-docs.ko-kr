---
title: "(구조적) C 및 C++ 예외 혼합 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ 예외 처리, 혼합 언어"
  - "catch 키워드[C++], 혼합형"
  - "예외, C 및 C++ 혼합"
  - "구조적 예외 처리, C 및 C++ 혼합"
  - "try-catch 키워드[C++], 혼합 언어"
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# (구조적) C 및 C++ 예외 혼합
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이식성이 높은 코드를 작성하려는 경우 C\+\+ 프로그램에서 구조화된 예외 처리를 사용하지 않는 것이 좋습니다.  하지만 **\/EHa**와 함께 컴파일하고 구조화된 예외 및 C\+\+ 소스 코드를 혼합하기를 원하며 두 종류의 예외를 처리하기 위한 일부 기능이 필요할 수도 있습니다.  구조화된 예외 처리기에는 개체 또는 형식화된 예외의 개념이 없기 때문에 C\+\+ 코드에서 throw된 예외를 처리할 수 없습니다. 그러나 C\+\+ **catch** 처리기는 구조화된 예외를 처리할 수 있습니다.  이와 같이 C\+\+ 예외 처리 구문\(**try**, `throw`, **catch**\)은 C 컴파일러에서 허용되지 않지만 구조화된 예외 처리 구문\(`__try`, `__except`, `__finally`\)은 C\+\+ 컴파일러에서 지원됩니다.  
  
 구조화된 예외를 C\+\+ 예외로 처리에 대한 자세한 내용은 [\_set\_se\_translator](../c-runtime-library/reference/set-se-translator.md)를 참조하십시오.  
  
 구조화된 예외와 C\+\+ 예외를 혼합하려면 다음을 참조하십시오.  
  
1.  C\+\+ 예외 및 구조화된 예외는 동일한 함수 내에서 혼합될 수 없습니다.  
  
2.  종료 처리기\(`__finally` 블록\)는 예외가 throw된 후 해제하는 동안에도 항상 실행됩니다.  
  
3.  C\+\+ 예외 처리는 [\/EH](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션\(이 옵션은 해제 의미 체계로 활성화됨\)으로 컴파일된 모든 모듈에서 해제 의미 체계를 catch하고 보존할 수 있습니다.  
  
4.  소멸자 함수가 모든 개체에 대해 호출하지 않는 일부 경우가 있을 수 있습니다.  예를 들어 초기화되지 않은 함수 포인터를 통해 함수 호출을 시도하는 동안 구조화된 예외가 발생한 경우 해당 함수는 호출 전 생성된 매개 변수 개체를 사용하고 이러한 개체에는 스택을 해제하는 동안 호출된 소멸자가 없습니다.  
  
## 추가 정보  
  
-   [C\+\+ 프로그램에서 setjmp 또는 longjmp 사용](../cpp/using-setjmp-longjmp.md)  
  
-   [SEH와 C\+\+ EH의 차이](../cpp/exception-handling-differences.md)  
  
## 참고 항목  
 [C\+\+ 예외 처리](../cpp/cpp-exception-handling.md)