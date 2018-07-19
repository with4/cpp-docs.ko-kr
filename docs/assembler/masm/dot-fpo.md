---
title: . FPO | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .FPO
dev_langs:
- C++
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df5185c0dc699764427989b2f46345d90ded1729
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32055940"
---
# <a name="fpo"></a>.FPO
합니다. FPO 지시문 섹션 이나.debug$ F 세그먼트에 디버그 레코드를 내보낼을 제어합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
FPO (  
cdwLocals  
,   
cdwParams  
,   
cbProlog  
,   
cbRegs  
,   
fUseBP  
,   
cbFrame  
)  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cdwLocals`  
 지역 변수는 부호 없는 32 비트 값의 수입니다.  
  
 `cdwParams`  
 DWORD, 부호 없는 16 비트 값의에서 매개 변수 크기입니다.  
  
 *cbProlog*  
 함수 프롤로그 코드는 부호 없는 8 비트 값의 바이트 수입니다.  
  
 `cbRegs`  
 저장 된 레지스터 번호입니다.  
  
 `fUseBP`  
 EBP 레지스터 할당 되었는지 여부를 나타냅니다. 0 또는 1입니다.  
  
 *cbFrame*  
 프레임 유형을 나타냅니다.  참조 [FPO_DATA](http://msdn.microsoft.com/library/windows/desktop/ms679352) 자세한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)