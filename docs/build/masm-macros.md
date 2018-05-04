---
title: MASM 매크로 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 21410432-72fc-4795-bc93-e78123f9f14f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 403220306a2585b1506a990664eaa2ec8f2ac1a3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="masm-macros"></a>MASM 매크로
사용을 단순화 하기 위해는 [원시 의사 작업](../build/raw-pseudo-operations.md)를 일반적인 방법 프롤로그 및 에필로그를 만드는 데 사용할 수 있도록 ksamd64.inc에에 정의 된 매크로의 집합입니다.  
  
## <a name="remarks"></a>설명  
  
|매크로|설명|  
|-----------|-----------------|  
|alloc_stack(n)|(N 하위 rsp 사용), n 바이트의 스택 프레임을 할당 하 고 내보냅니다 (.allocstack n) 정보를 적절 한 해제|  
|save_reg reg, loc|비휘발성 레지스터 reg RSP 오프셋된 loc 스택에 저장 되 고 내보냅니다 적절 한 정보를 해제 합니다. (.savereg reg, loc)|  
|push_reg reg|비휘발성 레지스터 reg 스택에 푸시하고 내보내는 적절 한 정보를 해제 합니다. 생성 합니다.|  
|rex_push_reg reg|2 바이트 푸시를 사용 하 여 스택에 비휘발성 레지스터를 저장 하 고 내보내는 적절 한 해제 정보 생성 합니다. 푸시가 함수에는 핫 패치 가능한 지 확인 하려면 첫 번째 명령 함수에 사용 해야 합니다.|  
|save_xmm128 reg, loc|RSP 오프셋된 loc에 스택의 XMM 등록 한 다음 비휘발성 레지스트리를 저장 하 고 내보냅니다 (.savexmm128 reg, loc) 정보를 적절 한 해제|  
|set_frame reg, 오프셋|프레임 레지스터 reg는 RSP be + (mov, 또는 사용 하는 유지) 오프셋을 설정 하 고 내보냅니다 (.set_frame reg, 오프셋) 정보를 적절 한 해제|  
|push_eflags|Pushfq 명령으로 eflags 밀어 넣고 내보냅니다 (.alloc_stack 8) 정보를 적절 한 해제|  
  
 매크로의 올바른 사용법 샘플 함수 프롤로그는 다음과 같습니다.  
  
```  
SkFrame struct   
Fill    dq ?; fill to 8 mod 16   
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
  
## <a name="see-also"></a>참고 항목  
 [MASM에 대한 해제 도우미](../build/unwind-helpers-for-masm.md)