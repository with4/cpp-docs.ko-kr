---
title: "PROC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROC directive"
ms.assetid: ee5bb6b6-fa15-4d73-b0cf-e650178539a9
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# PROC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

호출 하는 프로시저 블록의 시작과 끝을 표시  *레이블*.  문 블록에서을 호출할 수 있는  **호출** 명령 또는  [INVOKE](../../assembler/masm/invoke.md) 지시문.  
  
## 구문  
  
```  
  
   label PROC [[distance]] [[langtype]] [[visibility]] [[<prologuearg>]]   
[[USES reglist]] [[, parameter [[:tag]]]]...  
[FRAME [:ehandler-address] ]  
statements  
label ENDP  
```  
  
## 설명  
 프레임 \[:*ehandler 주소*\] ml64.exe에만 유효 하 고 MASM으로.pdata에서 함수 테이블 엔트리를 생성 하 고 함수의 구조적 위해.xdata에서 정보를 해제로 인해 예외 처리 해제 동작 합니다.  
  
 때의  **프레임** 특성 사용, 여와 야는 [.ENDPROLOG](../../assembler/masm/dot-endprolog.md) 지시문입니다.  
  
 참조 하십시오 [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md) ml64.exe 사용에 대 한 자세한 내용은.  
  
## 예제  
  
```  
; ml64 ex1.asm /link /entry:Example1 /SUBSYSTEM:CONSOLE  
_text SEGMENT  
Example1 PROC FRAME  
   push r10  
.pushreg r10  
   push r15  
.pushreg r15  
   push rbx  
.pushreg rbx  
   push rsi  
.pushreg rsi  
.endprolog  
   ; rest of function ...  
   ret  
Example1 ENDP  
_text ENDS  
END  
```  
  
 위의 코드 다음 함수 표를 내보내고 정보를 해제 합니다.  
  
```  
FileHeader->Machine 34404  
Dumping Unwind Information for file ex2.exe  
  
.pdata entry 1 0x00001000 0x00001023  
  
  Unwind data: 0x00002000  
  
    Unwind version: 1  
    Unwind Flags: None  
    Size of prologue: 0x08  
    Count of codes: 3  
    Frame register: rbp  
    Frame offset: 0x0  
    Unwind codes:  
  
      Code offset: 0x08, SET_FPREG, register=rbp, offset=0x00  
      Code offset: 0x05, ALLOC_SMALL, size=0x10  
      Code offset: 0x01, PUSH_NONVOL, register=rbp  
```  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)