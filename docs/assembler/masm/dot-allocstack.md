---
title: . ALLOCSTACK | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .ALLOCSTACK
dev_langs: C++
helpviewer_keywords: .ALLOCSTACK directive
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 20d9147b2c1a95d4fc9600935111a9c0c013be21
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="allocstack"></a>.ALLOCSTACK
생성 된 **UWOP_ALLOC_SMALL** 또는 **UWOP_ALLOC_LARGE** 를 프롤로그에서 현재 오프셋에 대 한 지정 된 크기가 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
.ALLOCSTACK size  
```  
  
## <a name="remarks"></a>설명  
 지정된 된 크기에 대 한 가장 효율적인 인코딩 MASM 선택 합니다.  
  
 . ALLOCSTACK ml64.exe 사용자가 프레임 함수 해제 하는 방법을 지정할 수 있으며에서 확장 되는 프롤로그만 사용할 수는 [PROC](../../assembler/masm/proc.md) 프레임 선언을 [합니다. 프롤로그 끝](../../assembler/masm/dot-endprolog.md) 지시문입니다. 이러한 지시문 코드를 생성 하지 않습니다. 만 생성할 `.xdata` 및 `.pdata`합니다. . ALLOCSTACK 실제로 해제 해제 되도록 작업을 구현 하는 지침 뒤에 야 합니다. 해제 지시문와 실제 매크로에서 해제 하는 코드를 래핑하는 것이 좋습니다.  
  
 `size` 피연산자 8의 배수 여야 합니다.  
  
 자세한 내용은 참조 [MASM (ml64.exe) x64](../../assembler/masm/masm-for-x64-ml64-exe.md)합니다.  
  
## <a name="sample"></a>샘플  
 다음 샘플에는 해제/예외 처리기를 지정 하는 방법을 보여 줍니다.  
  
```  
; ml64 ex3.asm /link /entry:Example1  /SUBSYSTEM:Console  
text SEGMENT  
PUBLIC Example3  
PUBLIC Example3_UW  
Example3_UW PROC NEAR  
   ; exception/unwind handler body  
  
   ret 0  
  
Example3_UW ENDP  
  
Example3 PROC FRAME : Example3_UW  
  
   sub rsp, 16  
.allocstack 16  
  
.endprolog  
  
   ; function body  
    add rsp, 16  
   ret 0  
  
Example3 ENDP  
text ENDS  
END  
```  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)