---
title: ".MODEL | Microsoft Docs"
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
  - ".MODEL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".MODEL directive"
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .MODEL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로그램 메모리 모델을 초기화합니다.  
  
## 구문  
  
```  
.MODEL memorymodel [[, langtype]] [[, stackoption]]  
```  
  
#### 매개 변수  
 `memorymodel`  
 코드 및 데이터 포인터의 크기를 결정 하는 필수 매개 변수입니다.  
  
 `langtype`  
 프로시저 및 공용 기호에 대 한 호출 및 명명 규칙을 설정 하는 선택적 매개 변수.  
  
 `stackoption`  
 선택적 매개 변수입니다.  
  
 `stackoption`is not used if `memorymodel` is `FLAT`.  
  
 지정 `NEARSTACK` 스택 세그먼트에는 하나의 실제 세그먼트로 그룹화 \(`DGROUP`\) 데이터와 함께.  스택 세그먼트 레지스터 \(`SS`\) 데이터 세그먼트 레지스터와 같은 주소 보유로 간주 됩니다 \(`DS`\).  `FARSTACK`스택에서 그룹화 하지 않습니다 `DGROUP`. 따라서 `SS` 과 일치 하지 않는 `DS`.  
  
## 설명  
 .`MODEL`사용 되지 않는 [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
 다음 표에서 각 매개 변수에 사용 가능한 값 16 비트 및 32 비트 플랫폼을 대상으로 하는 경우를 나열 합니다.  
  
|Parameter|32 비트 값입니다.|16 비트 값 \(이전 16 비트 개발 지원\)|  
|---------------|-----------------|--------------------------------|  
|`memorymodel`|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|  
|`langtype`|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|  
|`stackoption`|사용되지 않습니다.|`NEARSTACK`, `FARSTACK`|  
  
## 코드  
 컴파일러 샘플에서 MASM 관련 샘플을 다운로드 [Visual C\+\+ 샘플 및 관련 설명서를 2010 Visual Studio](란?LinkID%20=%20178749).  
  
 다음 예제에서는 해당 `.MODEL` 지시문.  
  
## 예제  
  
```  
; file simple.asm  
; For x86 (32-bit), assemble with debug information:   
;   ml -c -Zi simple.asm  
; For x64 (64-bit), assemble with debug information:   
;   ml64 -c -DX64 -Zi simple.asm  
;  
; In this sample, the 'X64' define excludes source not used   
;  when targeting the x64 architecture  
  
ifndef X64  
.686p  
.XMM  
.model flat, C  
endif  
  
.data  
; user data  
  
.code  
; user code  
  
fxn PROC public  
  xor eax, eax ; zero function return value  
  ret  
fxn ENDP  
  
end  
```  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)   
 [Visual C\+\+ 샘플 및 관련된 설명서를 2010 Visual Studio](란?LinkID%20=%20178749)