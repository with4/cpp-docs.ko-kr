---
title: . SAVEREG | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .SAVEREG
dev_langs: C++
helpviewer_keywords: .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ab1e777aa8bdddc4aa4fd71212f3275231b92dc4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="savereg"></a>.SAVEREG
중 하나를 생성 한 `UWOP_SAVE_NONVOL` 또는 `UWOP_SAVE_NONVOL_FAR` 지정된 된 레지스터에 대 한 코드 항목 해제 (`reg`) 및 오프셋 (`offset`) 현재 프롤로그 오프셋을 사용 하 여 합니다. MASM 가장 효율적인 인코딩 선택 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
.SAVEREG reg, offset  
```  
  
## <a name="remarks"></a>설명  
 . SAVEREG ml64.exe 사용자가 프레임 함수 해제 하는 방법을 지정할 수 있으며에서 확장 되는 프롤로그만 사용할 수는 [PROC](../../assembler/masm/proc.md) 프레임 선언을 [합니다. 프롤로그 끝](../../assembler/masm/dot-endprolog.md) 지시문입니다. 이러한 지시문 코드를 생성 하지 않습니다. 만 생성할 `.xdata` 및 `.pdata`합니다. . SAVEREG 실제로 해제 해제 되도록 작업을 구현 하는 지침 뒤에 야 합니다. 해제 지시문와 실제 매크로에서 해제 하는 코드를 래핑하는 것이 좋습니다.  
  
 자세한 내용은 참조 [MASM (ml64.exe) x64](../../assembler/masm/masm-for-x64-ml64-exe.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)