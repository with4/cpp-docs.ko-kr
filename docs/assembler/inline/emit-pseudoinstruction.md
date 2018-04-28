---
title: _emit pseudoinstruction | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
f1_keywords:
- _emit
dev_langs:
- C++
helpviewer_keywords:
- byte defining (inline assembly)
- _emit pseudoinstruction
ms.assetid: 004c48f3-364c-4e82-9a51-e326f9cc7b2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ad75f4abf2e86cb08ba646e50e9390650993d05
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="emit-pseudoinstruction"></a>_emit Pseudoinstruction
## <a name="microsoft-specific"></a>Microsoft 전용  
 **_emit** pseudoinstruction은 현재 텍스트 세그먼트의 현재 위치에 1 바이트를 정의 합니다. **_emit** pseudoinstruction 유사한는 [DB](../../assembler/masm/db.md) MASM 지시문입니다.  
  
 다음 조각은 0x4A, 0x43, 0x4B 바이트를 코드에 추가합니다.  
  
```  
#define randasm __asm _emit 0x4A __asm _emit 0x43 __asm _emit 0x4B  
 .  
 .  
 .  
__asm {  
     randasm  
     }  
```  
  
> [!CAUTION]
>  `_emit`이 레지스터를 수정하는 명령을 생성하는 경우 최적화 기능을 사용하여 응용 프로그램을 컴파일하면 컴파일러는 영향을 받는 레지스터를 확인할 수 없습니다. 예를 들어 경우 `_emit` 수정 하는 명령을 생성는 **rax** 레지스터 컴파일러 되었음을 알 수 없습니다 **rax** 변경 되었습니다. 이 때문에 컴파일러는 인라인 어셈블러 코드가 실행된 후 해당 레지스터에 포함된 값을 잘못 가정할 수 있습니다. 따라서 응용 프로그램이 실행될 때 예기치 않은 동작이 발생할 수 있습니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)