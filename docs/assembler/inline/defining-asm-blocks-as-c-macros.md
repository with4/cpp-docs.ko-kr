---
title: "C 매크로로 __asm 블록 정의 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm 키워드[C++], C 매크로"
  - "매크로, __asm 블록"
  - "Visual C, 매크로"
ms.assetid: 677ba11c-21c8-4609-bba7-cd47312243b0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# C 매크로로 __asm 블록 정의
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Microsoft 관련**  
  
 매크로 C 소스 코드에 어셈블리 코드를 삽입 하는 편리한 방법을 제공 하지만 매크로 논리적으로 확장 하기 때문에 특별 한 주의가 요구 됩니다.  문제 없이 매크로 작성 하려면 다음이 규칙을 따릅니다.  
  
-   묶는  `__asm`중괄호에서를 차단 합니다.  
  
-   배치 된  `__asm`키워드 각 어셈블리 명령 앞에.  
  
-   이전 스타일 C 주석을 사용 하 여 \(  `/* comment */`\) 대신 어셈블리 스타일 주석 \(   `; comment`\) 또는 한 줄으로 된 주석은 C \(   `// comment`\).  
  
 다음 예제를 설명 하기 위해 간단한 매크로 정의 합니다.  
  
```  
#define PORTIO __asm      \  
/* Port output */         \  
{                         \  
   __asm mov al, 2        \  
   __asm mov dx, 0xD007   \  
   __asm out dx, al       \  
}  
```  
  
 처음에, 마지막 3  `__asm`키워드를 불필요 한 것 같습니다.  하지만 필요 한 줄에 매크로 확장 때문에.  
  
```  
__asm /* Port output */ { __asm mov al, 2  __asm mov dx, 0xD007 __asm out dx, al }  
```  
  
 세 번째 및 네 번째  `__asm`키워드는 문 구분 기호로 필요 합니다.  문 구분 기호 인식  `__asm`요소는 줄 바꿈 문자 및  `__asm`키워드.  사용 하 여 각 명령을 구분 해야 블록을 매크로로 정의 된 논리 줄 이기 때문에  `__asm`.  
  
 중괄호는도 필수적입니다.  생략 하면 컴파일러가 매크로 호출의 오른쪽에는 같은 줄에 C 또는 c \+ \+ 문으로 혼동할 수 있습니다.  닫는 중괄호 없이 컴파일러가 어셈블리 코드 중지 되 고 알 수 없습니다 C 또는 c \+ \+ 문가  `__asm`블록으로 조립 지침.  
  
 세미콜론으로 시작 하는 어셈블리 스타일 주석 \(**;**\)는 줄의 끝까지 계속 합니다.  컴파일러는 논리 줄의 끝까지 주석 다음 모든 것을 무시 하기 때문에 매크로에서 문제가 발생 합니다.  C 또는 c \+ \+ 주석 줄도 마찬가지입니다 \(  `// comment`\).  이전 스타일 C 메모를 사용 하 여 오류를 방지 하려면 \(  `/* comment */`\)에서  `__asm`매크로로 정의 된 블록입니다.  
  
 `__asm`블록 기록 C 매크로 인수를 사용할 수 있습니다.  그러나 일반 C 매크로, 달리는  `__asm`매크로 값을 반환할 수 없습니다.  C 또는 c \+ \+ 식에 이러한 매크로 사용할 수 없습니다.  
  
 무분별이 형식의 매크로 호출 하지 않도록 주의 하십시오.  예를 들어, 사용 하 여 선언 된 어셈블리 언어 매크로 함수에서를 호출 하 여  `__fastcall`규칙에 예기치 않은 결과가 발생할 수 있습니다.  \(참조  [를 사용 하 여 레지스터를 인라인 어셈블리에서는 유지 및](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md).\)  
  
 **Microsoft 특정 끝**  
  
## 참고 항목  
 [인라인 어셈블러](../../assembler/inline/inline-assembler.md)