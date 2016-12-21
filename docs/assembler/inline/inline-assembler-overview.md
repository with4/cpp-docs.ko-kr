---
title: "인라인 어셈블러 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm 키워드[C++], 인라인 어셈블러 호출"
  - "인라인 어셈블러"
  - "인라인 어셈블리, 인라인 어셈블러"
  - "인라인 어셈블러 호출"
ms.assetid: d990331a-0e33-4760-8d7a-b720b0288335
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 인라인 어셈블러 개요
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Microsoft 관련**  
  
 인라인 어셈블러 어셈블리 및 링크의 추가 단계 없이 C 및 c \+ \+ 소스 프로그램에서 어셈블리 언어 지침을 포함할 수 있습니다.  인라인 어셈블러 컴파일러에 기본 제공\-별도 어셈블러 Microsoft 매크로 어셈블러 \(MASM\) 등 필요는 없습니다.  
  
 인라인 어셈블러는 별도 어셈블리 및 링크 단계 필요 하지 않습니다, 이므로 별도 어셈블러 보다 편리 합니다.  인라인 어셈블리 코드가 모든 C 또는 c \+ \+ 변수 또는 함수에에서 이름이 있는 범위를 프로그램의 C 및 c \+ \+ 코드와 통합 하기 쉽게 사용할 수 있습니다.  및 C 및 c \+ \+ 문으로 어셈블리 코드를 혼합할 수 있기 때문에 불편 하거나 C 또는 c \+ \+ 만으로는 불가능 한 작업을 수행할 수 있습니다 것입니다.  
  
 [\_\_asm](../../assembler/inline/asm.md) 키워드 호출 인라인 어셈블러와 C 또는 c \+ \+ 문의 어디에 사용할 수 있습니다.  단독으로 나타날 수 없습니다.  어셈블리 명령을 중괄호 또는, 적어도, 사이 있는 명령 그룹으로 따라야 할 빈 중괄호 쌍.  용어 " `__asm` 블록" 여기 모든 명령 또는 명령의 중괄호 안에 여부 그룹을 참조합니다.  
  
 다음 코드는 간단한  `__asm`블록 중괄호로 묶습니다.  \(코드는 사용자 지정 함수 프롤로그 순서입니다.\)  
  
```  
// asm_overview.cpp  
// processor: x86  
void __declspec(naked) main()  
{  
    // Naked functions must provide their own prolog...  
    __asm {  
        push ebp  
        mov ebp, esp  
        sub esp, __LOCAL_SIZE  
    }  
  
    // ... and epilog  
    __asm {  
        pop ebp  
        ret  
    }  
}  
```  
  
 넣을 수 있습니다  `__asm`각 어셈블리 명령 앞에:  
  
```  
__asm push ebp  
__asm mov  ebp, esp  
__asm sub  esp, __LOCAL_SIZE  
```  
  
 이후에  `__asm`키워드는 문을 구분, 같은 줄에는 어셈블리 지침을 전환할 수도 있습니다:  
  
```  
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE  
```  
  
 **Microsoft 특정 끝**  
  
## 참고 항목  
 [인라인 어셈블러](../../assembler/inline/inline-assembler.md)