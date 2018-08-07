---
title: . SAVEXMM128 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SAVEXMM128
dev_langs:
- C++
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d50d4bbc7f9c89e9ef36a1dd8cf3dfeb56de79b5
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057941"
---
# <a name="savexmm128"></a>.SAVEXMM128
중 하나를 생성 한 `UWOP_SAVE_XMM128` 또는 `UWOP_SAVE_XMM128_FAR` 지정된 XMM 레지스터에 대 한 코드 항목을 해제 하 고 현재 프롤로그 오프셋을 사용 하 여 오프셋 합니다. MASM 가장 효율적인 인코딩 선택 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
.savexmm128 xmmreg , offset  
```  
  
## <a name="remarks"></a>설명  
 . SAVEXMM128를 사용 하면 ml64.exe 프레임 함수, 해제 및에서 확장 되는 프롤로그만 사용할 수 방법을 지정할 수는 [PROC](../../assembler/masm/proc.md) 프레임 선언을 [합니다. 프롤로그 끝](../../assembler/masm/dot-endprolog.md) 지시문입니다. 이러한 지시문 코드를 생성 하지 않습니다. 만 생성할 `.xdata` 및 `.pdata`합니다. . SAVEXMM128 실제로 해제 해제 되도록 작업을 구현 하는 지침 뒤에 야 합니다. 해제 지시문와 실제 매크로에서 해제 하는 코드를 래핑하는 것이 좋습니다.  
  
 `offset` 16의 배수 여야 합니다.  
  
 자세한 내용은 참조 [MASM (ml64.exe) x64](../../assembler/masm/masm-for-x64-ml64-exe.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)