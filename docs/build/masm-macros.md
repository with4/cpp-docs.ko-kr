---
title: "MASM 매크로 | Microsoft Docs"
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
ms.assetid: 21410432-72fc-4795-bc93-e78123f9f14f
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# MASM 매크로
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[원시 의사 작업](../build/raw-pseudo-operations.md)을 간편하게 사용할 수 있도록 ksamd64.inc에 매크로 집합이 정의되어 있습니다. 이 매크로를 사용하여 일반적인 프로시저 프롤로그 및 에필로그를 만들 수 있습니다.  
  
## 설명  
  
|매크로|설명|  
|---------|--------|  
|alloc\_stack\(n\)|sub rsp, n을 사용하여 n바이트의 스택 프레임을 할당하고 적절한 해제 정보\(.allocstack n\)를 생성합니다.|  
|save\_reg reg, loc|비volatile 레지스터 reg를 스택의 RSP\(오프셋 loc\)에 저장하고 적절한 해제 정보\(.savereg reg, loc\)를  생성합니다.|  
|push\_reg reg|비volatile 레지스터 reg를 스택에 푸시하고 적절한 해제 정보\(.pushreg reg\)를  생성합니다.|  
|rex\_push\_reg reg|2 바이트 푸시를 사용 하 여 스택에서 비 volatile 레지스터를 저장 하 고 방출이 사용 해야 경우 밀어넣기 함수 핫 patchable 수 있도록 함수에서 첫 번째 명령 정보를 생성 합니다\) 적절 한 해제 합니다.|  
|save\_xmm128 reg, loc|비volatile XMM 레지스터 reg를 스택의 RSP\(오프셋 loc\)에 저장하고 적절한 해제 정보\(.savexmm128 reg, loc\)를 생성합니다.|  
|set\_frame reg, offset|mov나 lea를 사용하여 프레임 레지스터 reg를 RSP\+offset으로 설정하고 적절한 해제 정보\(.set\_frame reg, offset\)를 생성합니다.|  
|push\_eflags|pushfq 명령을 사용하여 eflags를 푸시하고 적절한 해제 정보\(.alloc\_stack 8\)를 생성합니다.|  
  
 다음 예제 함수 프롤로그에서는 매크로의 올바른 사용법을 보여 줍니다.  
  
```  
SkFrame struct   
Fill    dq ?; fill to 8 mod 16   
SavedRdi dq ?; saved register RDI   
SavedRsi dq ?; saved register RSI   
SkFrame ends  
  
sampleFrame struct  
Filldq?; fill to 8 mod 16  
SavedRdidq?; Saved Register RDI   
SavedRsi  dq?; Saved Register RSI  
sampleFrame ends  
  
sample2 PROC FRAME  
alloc_stack(sizeof sampleFrame)  
save_reg rdi, sampleFrame.SavedRdi  
save_reg rsi, sampleFrame.SavedRsi  
.end_prolog  
  
; function body  
  
mov rsi, sampleFrame.SavedRsi[rsp]  
mov rdi, sampleFrame.SavedRdi[rsp]  
  
; Here’s the official epilog  
  
add rsp, (sizeof sampleFrame)  
ret  
sample2 ENDP  
```  
  
## 참고 항목  
 [MASM에 대한 해제 도우미](../build/unwind-helpers-for-masm.md)