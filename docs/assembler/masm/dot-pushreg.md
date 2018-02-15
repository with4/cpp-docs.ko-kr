---
title: . PUSHREG | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .PUSHREG
dev_langs:
- C++
helpviewer_keywords:
- .PUSHREG directive
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 84cc00d51f72993e1e7673d8d4f3d01478d32041
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="pushreg"></a>.PUSHREG
생성 된 `UWOP_PUSH_NONVOL` 현재 프롤로그의 오프셋을 사용 하 여 번호를 지정 된 등록에 대 한 코드 항목을 해제 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
.PUSHREG register  
```  
  
## <a name="remarks"></a>설명  
 . PUSHREG를 사용 하면 ml64.exe 프레임 함수, 해제 및에서 확장 되는 프롤로그만 사용할 수 방법을 지정할 수는 [PROC](../../assembler/masm/proc.md) 프레임 선언을 [합니다. 프롤로그 끝](../../assembler/masm/dot-endprolog.md) 지시문입니다. 이러한 지시문 코드를 생성 하지 않습니다. 만 생성할 `.xdata` 및 `.pdata`합니다. . PUSHREG 실제로 해제 해제 되도록 작업을 구현 하는 지침 뒤에 야 합니다. 해제 지시문와 실제 매크로에서 해제 하는 코드를 래핑하는 것이 좋습니다.  
  
 자세한 내용은 참조 [MASM (ml64.exe) x64](../../assembler/masm/masm-for-x64-ml64-exe.md)합니다.  
  
## <a name="sample"></a>샘플  
  
### <a name="description"></a>설명  
 다음 예제에는 volatile이 아닌 tegisters 강제 하는 방법을 보여 줍니다.  
  
### <a name="code"></a>코드  
  
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
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)