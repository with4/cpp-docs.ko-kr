---
title: "try-finally 문 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__try"
  - "__leave_cpp"
  - "__leave"
  - "__finally_cpp"
  - "__try_cpp"
  - "__finally"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__finally 키워드[C++]"
  - "__finally 키워드[C++], try-finally 문 구문"
  - "__leave 키워드[C++]"
  - "__leave 키워드[C++], try-finally 문"
  - "__try 키워드[C++]"
  - "구조적 예외 처리, try-finally"
  - "try-catch 키워드[C++], try-finally 키워드"
  - "try-finally 키워드[C++]"
ms.assetid: 826e0347-ddfe-4f6e-a7bc-0398e0edc7c2
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# try-finally 문
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 다음 구문에서는 `try-finally` 문을 설명합니다.  
  
```  
__try {  
   // guarded code  
}  
__finally {  
   // termination code  
}  
```  
  
## 문법  
 *try\-finally\-statement*:  
 `__try` *compound\-statement*  
  
 `__finally` *compound\-statement*  
  
 `try-finally` 문은 C 및 C\+\+ 언어의 Microsoft 확장으로서, 코드 블록 실행이 중단된 경우 대상 응용 프로그램이 정리 코드를 실행하게 해줍니다.  정리는 메모리 할당 해제, 파일 닫기 및 파일 핸들 해제와 같은 작업으로 구성됩니다.  `try-finally` 문은 루틴으로부터 중간에 반환되게 만들 수 있는 오류가 있는지 확인하기 위해 검사가 수행되는 위치가 많은 루틴에 특히 유용합니다.  
  
 관련 정보와 코드 샘플을 보려면 [try\-except 문](../cpp/try-except-statement.md)을 참조하십시오.  구조적 예외 처리에 대한 자세한 내용은 [구조적 예외 처리](../cpp/structured-exception-handling-c-cpp.md)를 참조하십시오.  관리되는 응용 프로그램의 예외 처리에 대한 자세한 내용은 [\/clr에서 예외 처리](../windows/exception-handling-cpp-component-extensions.md)를 참조하십시오.  
  
> [!NOTE]
>  구조적 예외 처리는 Win32에서 C 및 C\+\+ 소스 파일에 대해 작동하지만  특별히 C\+\+용으로 설계되지는 않았습니다.  C\+\+ 예외 처리를 사용하여 코드의 이식성이 향상되는지 확인할 수 있습니다.  또한 C\+\+ 예외 처리는 모든 형식의 예외를 처리할 수 있다는 점에서 보다 유연합니다.  C\+\+ 프로그램의 경우 C\+\+ 예외 처리 메커니즘을 사용하는 것이 좋습니다\([try, catch, throw](../cpp/try-throw-and-catch-statements-cpp.md) 문\).  
  
 `__try` 절 뒤의 복합 문은 보호된 섹션입니다.  `__finally` 절 뒤의 복합 문은 종료 처리기입니다.  처리기는 보호된 섹션이 예외\(비정상적인 종료\)로 인해 종료되건 표준 이동\(정상적인 종료\)으로 인해 종료되건 간에 보호된 섹션이 끝나면 실행되는 작업 집합을 지정합니다.  
  
 제어는 단순한 순차적 실행\(제어 이동\)에 의해 `__try` 문에 도달합니다.  제어가 `__try`에 들어가면 연결된 처리기가 활성화됩니다.  제어 흐름이 try 블록 끝에 도달하면 다음과 같이 실행됩니다.  
  
1.  종료 처리기가 호출됩니다.  
  
2.  종료 처리기가 완료되면 실행이 `__finally` 문 후에 계속됩니다.  보호된 섹션이 끝나는 방법\(예: 보호된 본문 밖의 `goto`를 통해 또는 `return` 문을 통해\)에 관계없이 제어 흐름이 보호된 섹션 밖으로 이동하기 `before` 종료 처리기가 실행됩니다.  
  
     **\_\_finally** 문이 적합한 예외 처리기 검색을 차단하지 않습니다.  
  
 `__try` 블록에 예외가 발생할 경우 운영 체제에서 적합한 예외 처리기를 찾아야 합니다. 그렇지 않으면 프로그램이 실패합니다.  처리기를 찾으면 모든 `__finally` 블록이 실행되고 처리기에서 실행이 다시 시작됩니다.  
  
 예를 들어, 일련의 함수 호출 링크에서는 함수 A를 D에 연결한다고 가정합니다\(아래 그림 참조\).  각 함수에는 종료 처리기가 하나씩 있습니다.  예외가 D 함수에서 발생하고 A에서 처리될 경우 시스템이 스택 D, C, B를 해제하면 그 순서대로 종료 처리기가 호출됩니다.  
  
 ![종료 처리기 실행 순서](../cpp/media/vc38cx1.png "vc38CX1")  
종료 처리기 실행 순서  
  
> [!NOTE]
>  try\-finally의 동작은 C\# 같은 **finally**의 사용을 지원하는 일부 다른 언어와 다릅니다.  단일 `__try`에는 `__finally`와 `__except` 중 하나만 있을 수 있습니다.  모두 함께 사용되는 경우 외부 try\-except 문은 내부 try\-finally 문을 포함해야 합니다.  또한 각 블록을 실행할 때 지정되는 규칙은 서로 다릅니다.  
  
## \_\_leave 키워드  
 `__leave` 키워드는 `try-finally` 문의 보호된 섹션 내에서만 유효하며, 보호된 섹션의 끝으로 이동하도록 합니다.  종료 처리기의 첫 번째 문에서 계속 실행됩니다.  
  
 `goto` 문은 보호된 섹션에서 외부로 이동할 수도 있지만 스택 해제를 호출하기 때문에 성능이 저하됩니다.  `__leave` 문은 스택 해제를 발생시키지 않으므로 더 효율적입니다.  
  
## 비정상적인 종료  
 [longjmp](../c-runtime-library/reference/longjmp.md) 런타임 함수를 사용하여 `try-finally` 문을 종료하는 것은 비정상 종료로 간주됩니다.  `__try` 문 안으로 이동할 수 없지만 이 문 밖으로 이동할 수는 있습니다.  출발 지점\(`__try` 블록의 정상 종료\)과 도착 지점\(예외를 처리하는 `__except` 블록\) 간에 활성화된 모든 `__finally` 문을 실행되어야 합니다.  이것을 로컬 해제라고 합니다.  
  
 블록 외부로의 이동을 포함하여 어떤 이유로 **try** 블록이 중간에 종료되는 경우 시스템은 스택 해제 과정의 일부로 관련 **finally** 블록을 실행합니다.  이러한 경우 [AbnormalTermination](http://msdn.microsoft.com/library/windows/desktop/ms679265) 함수가 **finally** 블록 내에서 호출된 경우 TRUE를 반환하고, 그렇지 않으면 FALSE를 반환합니다.  
  
 `try-finally` 문을 실행하는 중간에 프로세스가 종료될 경우에는 종료 처리기가 호출되지 않습니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [종료 처리기 작성](../cpp/writing-a-termination-handler.md)   
 [구조적 예외 처리](../cpp/structured-exception-handling-c-cpp.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [Termination\-Handler Syntax](http://msdn.microsoft.com/library/windows/desktop/ms681393)