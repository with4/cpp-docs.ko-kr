---
title: "Directives Reference | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Directives Reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MASM (Microsoft Macro Assembler), directives reference"
ms.assetid: da6efcd1-18f7-41de-81cd-a002a02f9a22
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Directives Reference
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**x64**  
  
||||  
|-|-|-|  
|[.ALLOCSTACK](../../assembler/masm/dot-allocstack.md)|[.ENDPROLOG](../../assembler/masm/dot-endprolog.md)|[\-프로세서](../../assembler/masm/proc.md)|  
|[.PUSHFRAME](../../assembler/masm/dot-pushframe.md)|[.PUSHREG](../../assembler/masm/dot-pushreg.md)|[.SAVEREG](../../assembler/masm/dot-savereg.md)|  
|[.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)|[.SETFRAME](../../assembler/masm/dot-setframe.md)||  
  
### 코드 레이블  
  
|||  
|-|-|  
|[맞춤](../../assembler/masm/align-masm.md)|[경우에](../../assembler/masm/even.md)|  
|[레이블](../../assembler/masm/label-masm.md)|[조직도](../../assembler/masm/org.md)|  
  
### 조건부 어셈블리  
  
||||  
|-|-|-|  
|[다른](../../assembler/masm/else-masm.md)|[ELSEIF](../../assembler/masm/elseif-masm.md)|[ELSEIF2](../../assembler/masm/elseif2.md)|  
|[IF](../../assembler/masm/if-masm.md)|[IF2](../../assembler/masm/if2.md)|[IFB](../../assembler/masm/ifb.md)\/[IFNB](../../assembler/masm/ifnb.md)|  
|[IFDEF](../../assembler/masm/ifdef.md)\/[IFNDEF](../../assembler/masm/ifndef.md)|[IFDIF](../../assembler/masm/ifdif.md)\/[IFDIF &#91;&#91;I&#93;](../../assembler/masm/ifdif.md)|[IFE](../../assembler/masm/ife.md)|  
|[IFIDN](../../assembler/masm/ifidn.md)\/[IFIDN &#91;&#91;I&#93;](../../assembler/masm/ifidn.md)|||  
  
### 조건부 흐름 제어  
  
||||  
|-|-|-|  
|[.나누기](../../assembler/masm/dot-break.md)|[.계속](../../assembler/masm/dot-continue.md)|[.다른](../../assembler/masm/dot-else.md)|  
|[.ELSEIF](../../assembler/masm/dot-if.md)|[.ENDIF](../../assembler/masm/dot-endif.md)|[.ENDW](../../assembler/masm/dot-endw.md)|  
|[.IF](../../assembler/masm/dot-if.md)|[.반복](../../assembler/masm/dot-repeat.md)|[.때까지](../../assembler/masm/dot-until.md)|  
|[.UNTILCXZ](../../assembler/masm/dot-untilcxz.md)|[.WHILE](../../assembler/masm/dot-while.md)||  
  
### 오류 조건  
  
||||  
|-|-|-|  
|[.오류](../../assembler/masm/dot-err.md)|[.ERR2](../../assembler/masm/dot-err2.md)|[.ERRB](../../assembler/masm/dot-errb.md)|  
|[.ERRDEF](../../assembler/masm/dot-errdef.md)|[.ERRDIF](../../assembler/masm/dot-errdif.md)\/[.ERRDIF &#91;&#91;I&#93;&#93;](../../assembler/masm/dot-errdif.md)|[.ERRE](../../assembler/masm/dot-erre.md)|  
|[.ERRIDN](../../assembler/masm/dot-erridn.md)\/[.&#91;&#91;I&#93;&#93; ERRIDN](../../assembler/masm/dot-erridn.md)|[.ERRNB](../../assembler/masm/dot-errnb.md)|[.ERRNDEF](../../assembler/masm/dot-errndef.md)|  
|[.ERRNZ](../../assembler/masm/dot-errnz.md)|||  
  
### 데이터 할당  
  
||||  
|-|-|-|  
|[맞춤](../../assembler/masm/align-masm.md)|[바이트](../../assembler/masm/byte-masm.md)\/[SBYTE](../../assembler/masm/sbyte-masm.md)|[DWORD](../../assembler/masm/dword.md)\/[SDWORD](../../assembler/masm/sdword.md)|  
|[경우에](../../assembler/masm/even.md)|[FWORD](../../assembler/masm/fword.md)|[레이블](../../assembler/masm/label-masm.md)|  
|[조직도](../../assembler/masm/org.md)|[QWORD](../../assembler/masm/qword.md)|[REAL4](../../assembler/masm/real4.md)|  
|[REAL8](../../assembler/masm/real8.md)|[REAL10](../../assembler/masm/real10.md)|[TBYTE](../../assembler/masm/tbyte.md)|  
|[WORD](../../assembler/masm/word.md)\/[검](../../assembler/masm/sword.md)|||  
  
### 것과 같습니다.  
  
||  
|-|  
|[\=](../../assembler/masm/equal.md)|  
|[EQU](../../assembler/masm/equ.md)|  
|[TEXTEQU](../../assembler/masm/textequ.md)|  
  
### 목록 컨트롤  
  
||||  
|-|-|-|  
|[.CREF](../../assembler/masm/dot-cref.md)|[.목록](../../assembler/masm/dot-list.md)|[.LISTALL](../../assembler/masm/dot-listall.md)|  
|[.허용](../../assembler/masm/dot-listif.md)|[.LISTMACRO](../../assembler/masm/dot-listmacro.md)|[.LISTMACROALL](../../assembler/masm/dot-listmacroall.md)|  
|[.NOCREF](../../assembler/masm/dot-nocref.md)|[.NOLIST](../../assembler/masm/dot-nolist.md)|[.NOLISTIF](../../assembler/masm/dot-nolistif.md)|  
|[.NOLISTMACRO](../../assembler/masm/dot-nolistmacro.md)|[페이지](../../assembler/masm/page.md)|[자막](../../assembler/masm/subtitle.md)|  
|[.TFCOND](../../assembler/masm/dot-tfcond.md)|[제목](../../assembler/masm/title.md)||  
  
### 매크로  
  
||||  
|-|-|-|  
|[ENDM](../../assembler/masm/endm.md)|[EXITM](../../assembler/masm/exitm.md)|[이동](../../assembler/masm/goto-masm.md)|  
|[로컬](../../assembler/masm/local-masm.md)|[매크로](../../assembler/masm/macro.md)|[지우기](../../assembler/masm/purge.md)|  
  
### 기타  
  
||||  
|-|-|-|  
|[ALIAS](../../assembler/masm/alias-masm.md)|[가정](../../assembler/masm/assume.md)|[주석](../../assembler/masm/comment-masm.md)|  
|[에코](../../assembler/masm/echo.md)|[End](../../assembler/masm/end-masm.md)|[.FPO](../../assembler/masm/dot-fpo.md)|  
|[포함](../../assembler/masm/include-masm.md)|[INCLUDELIB](../../assembler/masm/includelib-masm.md)|[MMWORD](../../assembler/masm/mmword.md)|  
|[옵션](../../assembler/masm/option-masm.md)|[POPCONTEXT](../../assembler/masm/popcontext.md)|[PUSHCONTEXT](../../assembler/masm/pushcontext.md)|  
|[.기 수](../../assembler/masm/dot-radix.md)|[.SAFESEH](../../assembler/masm/dot-safeseh.md)|[XMMWORD](../../assembler/masm/xmmword.md)|  
|[YMMWORD](../../assembler/masm/ymmword.md)|||  
  
### 절차  
  
||||  
|-|-|-|  
|[ENDP](../../assembler/masm/endp.md)|[호출](../../assembler/masm/invoke.md)|[\-프로세서](../../assembler/masm/proc.md)|  
|[프로토콜](../../assembler/masm/proto.md)|||  
  
### 프로세서  
  
||||  
|-|-|-|  
|[.386](../../assembler/masm/dot-386.md)|[.386P](../../assembler/masm/dot-386p.md)|[.387](../../assembler/masm/dot-387.md)|  
|[.486](../../assembler/masm/dot-486.md)|[.486P](../../assembler/masm/dot-486p.md)|[.586](../../assembler/masm/dot-586.md)|  
|[.586P](../../assembler/masm/dot-586p.md)|[.686](../../assembler/masm/dot-686.md)|[.686P](../../assembler/masm/dot-686p.md)|  
|[.K3D](../../assembler/masm/dot-k3d.md)|[.MMX](../../assembler/masm/dot-mmx.md)|[.XMM](../../assembler/masm/dot-xmm.md)|  
  
### 블록을 반복 합니다.  
  
||||  
|-|-|-|  
|[ENDM](../../assembler/masm/endm.md)|[에 대 한](../../assembler/masm/for-masm.md)|[FORC](../../assembler/masm/forc.md)|  
|[이동](../../assembler/masm/goto-masm.md)|[반복](../../assembler/masm/repeat.md)|[WHILE](../../assembler/masm/while-masm.md)|  
  
### 범위  
  
||||  
|-|-|-|  
|[통신](../../assembler/masm/comm.md)|[EXTERN](../../assembler/masm/extern-masm.md)|[EXTERNDEF](../../assembler/masm/externdef.md)|  
|[INCLUDELIB](../../assembler/masm/includelib-masm.md)|[공개](../../assembler/masm/public-masm.md)||  
  
### 세그먼트  
  
||||  
|-|-|-|  
|[.알파](../../assembler/masm/dot-alpha.md)|[가정](../../assembler/masm/assume.md)|[.DOSSEG](../../assembler/masm/dot-dosseg.md)|  
|[End](../../assembler/masm/end-masm.md)|[끝 모양](../../assembler/masm/ends-masm.md)|[GROUP](../../assembler/masm/group.md)|  
|[세그먼트](../../assembler/masm/segment.md)|[.SEQ](../../assembler/masm/dot-seq.md)||  
  
### 단순화 된 세그먼트  
  
||||  
|-|-|-|  
|[.코드](../../assembler/masm/dot-code.md)|[.CONST](../../assembler/masm/dot-const.md)|[.데이터](../../assembler/masm/dot-data.md)|  
|[.데이터?](../../assembler/masm/dot-data-q.md)|[.DOSSEG](../../assembler/masm/dot-dosseg.md)|[.끝내기](../../assembler/masm/dot-exit.md)|  
|[.FARDATA](../../assembler/masm/dot-fardata.md)|[.FARDATA?](../../assembler/masm/dot-fardata-q.md)|[.모델](../../assembler/masm/dot-model.md)|  
|[.스택](../../assembler/masm/dot-stack.md)|[.시작](../../assembler/masm/dot-startup.md)||  
  
### String  
  
|||  
|-|-|  
|[CATSTR](../../assembler/masm/catstr.md)|[INSTR](../../assembler/masm/instr.md)|  
|[SIZESTR](../../assembler/masm/sizestr.md)|[SUBSTR](../../assembler/masm/substr.md)|  
  
### 구조와 레코드  
  
||||  
|-|-|-|  
|[끝 모양](../../assembler/masm/ends-masm.md)|[레코드](../../assembler/masm/record-masm.md)|[구조체](../../assembler/masm/struct-masm.md)|  
|[형식 정의](../../assembler/masm/typedef-masm.md)|[공용 구조체](../../assembler/masm/union.md)||  
  
## 참고 항목  
 [Microsoft Macro Assembler Reference](../../assembler/masm/microsoft-macro-assembler-reference.md)