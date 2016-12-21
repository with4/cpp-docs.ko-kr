---
title: ".SAVEXMM128 | Microsoft Docs"
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
  - ".SAVEXMM128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".SAVEXMM128 directive"
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .SAVEXMM128
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

하나를 생성 하는 `UWOP_SAVE_XMM128` 또는 `UWOP_SAVE_XMM128_FAR` 지정 된 XMM 레지스터에 대 한 코드 항목을 해제 하 고 현재 프롤로그 오프셋을 사용 하 여 오프셋.  MASM은 가장 효율적인 인코딩을 선택합니다.  
  
## 구문  
  
```  
.savexmm128 xmmreg , offset  
```  
  
## 설명  
 .SAVEXMM128 ml64.exe 사용자 프레임 함수 해제를 하 고 프롤로그에서 확장에 사용할 수 있습니다 방법을 지정할 수 있습니다에서 [PROC](../../assembler/masm/proc.md) 프레임 선언에는 [.ENDPROLOG](../../assembler/masm/dot-endprolog.md) 지시문입니다.  이러한 지시문 코드를 생성 하지 않습니다. 생성만 `.xdata` 및 `.pdata`.  .해제 되지 않도록 하는 작업을 실제로 구현 지침에 savexmm128가 있어야 합니다.  해제 지시문과 계약을 확인 하려면 매크로 해제 합니다 의미입니다 코드를 래핑하는 것이 좋습니다.  
  
 `offset`16의 배수 여야 합니다.  
  
 자세한 내용은 [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md)를 참조하십시오.  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)