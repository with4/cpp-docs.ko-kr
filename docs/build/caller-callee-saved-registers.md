---
title: 호출자가 호출 수신자 저장 레지스터 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f65e88c8609d6a2097e9e54c3f52cbd27dce36d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="callercallee-saved-registers"></a>호출자/호출 수신자 저장 레지스터
함수 호출의 휘발성 간주 되며, 그 밖에 고려해 야 RAX, RCX, RDX, R8, r 9, r 10, R11 레지스터 삭제 (하지 않는 한 안전성이 전체 프로그램 최적화와 같은 분석을 통해).  
  
 RBX, RBP, RDI, RSI, RSP, r 12, R13, R14, 및 R15 레지스터 일시적이 아닌 것으로 간주 하 고 저장 해야 합니다는 함수에 의해 복원 하는 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [호출 규칙](../build/calling-convention.md)