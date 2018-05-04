---
title: MxCsr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4f3c229d-0862-4733-acc7-9ed7a0b870ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9df2225526c20463bdbd618322d031c3245d9493
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="mxcsr"></a>MxCsr
레지스터 상태 MxCsr 포함 됩니다. 호출 규칙 휘발성 부분과 비휘발성 부분에이 레지스터를 나눕니다. MXCSR 6 상태 플래그의 휘발성 부분 구성 [0:5], [6:15] MXCSR 레지스터의 나머지 부분에서는 일시적이 아닌 것으로 간주 됩니다.  
  
 비휘발성 부분이 프로그램 실행의 시작 부분에 다음과 같은 표준 값으로 설정 됩니다.  
  
```  
MXCSR[6]         : Denormals are zeros - 0  
MXCSR[7:12]      : Exception masks all 1's (all exceptions masked)  
MXCSR[13:14]   : Rounding  control - 0 (round to nearest)  
MXCSR[15]      : Flush to zero for masked underflow - 0 (off)  
```  
  
 MXCSR 내에서 비휘발성 필드를 수정 하는 호출 수신자는 호출자에 반환 하기 전에 복원 해야 합니다. 또한가 이러한 필드를 수정 하는 호출자가 해야 복원할 표준 값으로 계약에 의해 호출 수신자는 수정 된 값이 필요 하지 않는 한 호출 수신자를 호출 하기 전에.  
  
 제어 플래그의 비-변동성에 대 한 규칙을 두 가지 예외가 있습니다.  
  
-   비휘발성 MxCsr를 수정 하려면 지정 된 함수의 문서화 된 목적은 함수 플래그 지정 합니다.  
  
-   갖는 경우에 이러한 규칙 위반에 없는 이러한 규칙을 위반 하지 않은 예를 들어 전체 프로그램 분석을 통해 프로그램와 동일 하 게 작동/의미는 프로그램에서 결과 수정 합니다.  
  
 구체적으로 함수 설명서에서 설명 하지 않는 한 함수 경계를 넘어 휘발성 부분의 MXCSR 상태에 대 한 어떠한가 정도 하지를 만들 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [호출 규칙](../build/calling-convention.md)