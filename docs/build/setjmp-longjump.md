---
title: setjmp longjump | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55cf6a2503367777464f09f92e3e3614c3d9f11b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="setjmplongjump"></a>setjmp/longjump
Setjmp.h 나 setjmpex.h를 포함 하면 모든 호출 [setjmp](../c-runtime-library/reference/setjmp.md) 또는 [longjmp](../c-runtime-library/reference/longjmp.md) 소멸자를 호출 하 고 마지막으로 호출 하는 해제 됩니다.  이 점에서 차이가 x86, finally 절에서 setjmp.h 결과 포함 하 고 소멸자가 호출 되지 않습니다.  
  
 에 대 한 호출 `setjmp` 에서 현재 스택 포인터, 비휘발성 레지스터와 MxCsr 레지스터를 유지 합니다.  에 대 한 호출이 `longjmp` 가장 최근의 돌아가서 `setjmp` 호출 사이트 다시 설정 합니다. MxCsr, 비휘발성 레지스터와 스택 포인터가 레지스터, 상태로 가장 최근의 유지 `setjmp` 호출 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [호출 규칙](../build/calling-convention.md)