---
title: "MASM for x64 (ml64.exe) | Microsoft Docs"
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
  - "ml64.exe"
  - "ml"
ms.assetid: 89059103-f372-4968-80ea-0c7f90bb9c91
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# MASM for x64 (ml64.exe)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ml64.exe는 받아들이는 어셈블러 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 어셈블리 언어입니다.  Ml64.exe 컴파일러 옵션에 대 한 자세한 내용은 [ML and ML64 Command\-Line Reference](../../assembler/masm/ml-and-ml64-command-line-reference.md).  
  
 인라인 ASM을 지원 하지 않습니다 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)].  MASM 또는 컴파일러 내장 함수 사용 하 여 \([x64 Intrinsics](http://msdn.microsoft.com/ko-kr/5d1f5d3e-156e-4ebf-932e-fd09be7ced62)\).  
  
 두 가지 해결 방법을 별도 어셈블리를 MASM \(은 x 64를 완벽 하 게 지원\) 및 컴파일러 내장 형식입니다.  우리는 많은 고객이 허용 하는 내장 추가 했습니다 \(예: 특정 기능의 지침을 사용 하 여  권한, 비트 스캔\/테스트, 연동에 올려 놓고\) 에 플랫폼을 하는 방식으로 최대한 닫습니다.  
  
## ml64 관련 지시문  
 Ml64.exe에 다음 지시문을 사용 합니다.  
  
-   [.ALLOCSTACK](../../assembler/masm/dot-allocstack.md)  
  
-   [.ENDPROLOG](../../assembler/masm/dot-endprolog.md)  
  
-   [.PUSHFRAME](../../assembler/masm/dot-pushframe.md)  
  
-   [.PUSHREG](../../assembler/masm/dot-pushreg.md)  
  
-   [.SAVEREG](../../assembler/masm/dot-savereg.md)  
  
-   [.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)  
  
-   [.SETFRAME](../../assembler/masm/dot-setframe.md)  
  
 또한는 [PROC](../../assembler/masm/proc.md) 지시문 ml64.exe 함께 사용 하기 위해 업데이트 되었습니다.  
  
## 32 비트 주소 모드 \(주소 크기 우선 적용\)  
 32 비트 레지스터는 메모리 피연산자를 포함 하는 경우 MASM 0x67 주소 크기 재정을 내보냅니다.  예를 들어, 다음 예제에서는 내보낼 주소 크기 재정의 초래 합니다.  
  
```  
mov rax, QWORD PTR [ecx]  
mov eax, DWORD PTR [ecx*2+r10d]  
mov eax, DWORD PTR [ecx*2+r10d+0100h]  
prefetch [eax]  
movnti rax, QWORD PTR [r8d]  
```  
  
 MASM 64 비트 주소 지정 32 비트 치환 된 메모리 피연산자를 따로 나타나면 대상으로 있는지 가정 합니다.  현재 이러한 피연산자가 32 비트 주소 지정을 지원 하지 않습니다.  
  
 마지막으로 다음 코드와 같이 레지스터 크기, 메모리 피연산자를 혼합 하 여 오류를 생성 합니다.  
  
```  
mov eax, DWORD PTR [rcx*2+r10d]  
mov eax, DWORD PTR [ecx*2+r10+0100h]  
```  
  
## 참고 항목  
 [Microsoft Macro Assembler Reference](../../assembler/masm/microsoft-macro-assembler-reference.md)