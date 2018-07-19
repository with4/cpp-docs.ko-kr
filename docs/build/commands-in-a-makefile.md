---
title: 메이크파일의 명령 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- commands, makefiles
ms.assetid: 8085517e-42f4-493b-b8f8-44311fc08c64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99e1eb5b4800ff1046ca60d4d4874d386809e2e0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366876"
---
# <a name="commands-in-a-makefile"></a>메이크파일의 명령
설명 블록 또는 유추 규칙의 종속성이 오래 된 경우 실행 하는 명령 블록을 지정 합니다. NMAKE 않는 한 각 명령을 실행 하기 전에 표시 /S, **합니다. 자동**, **! CMDSWITCHES**, 또는 @ 사용 됩니다. NMAKE 설명 블록 명령 블록이 나오지 않습니다. 일치 하는 유추 규칙을 찾습니다.  
  
 명령 블록에는 각각 별도 줄에 명령을 하나 이상 포함합니다. 없는 빈 줄 종속성 또는 규칙와 명령 블록 사이 나타날 수 있습니다. 그러나 공백이 나 탭을 포함 하는 줄 나타날 수 있습니다. 이 줄은 null 명령으로 해석 하 고 오류가 발생 하지 않습니다. 빈 줄 명령 줄 사이 허용 됩니다.  
  
 하나 이상의 공백이 나 탭으로 명령줄을 시작합니다. 뒤에 줄 바꿈 문자가 백슬래시 (\)은 command;의 공간으로 해석 됩니다. 줄의 끝에 백슬래시를 사용 하 여 다음 줄으로 명령을 계속 합니다. NMAKE는 백슬래시를 문자 그대로 해석 백슬래시 뒤에 공백이 나 탭을 비롯 한 다른 문자가 하는 경우.  
  
 명령 앞에 세미콜론 (;) 뒤에 명령 블록이 여부 종속성 선 또는 유추 규칙에 나타날 수 있습니다.  
  
```  
project.obj : project.c project.h ; cl /c project.c  
```  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
 [명령 한정자](../build/command-modifiers.md)  
  
 [파일 이름 부분 구문](../build/filename-parts-syntax.md)  
  
 [메이크파일의 인라인 파일](../build/inline-files-in-a-makefile.md)  
  
## <a name="see-also"></a>참고 항목  
 [NMAKE 참조](../build/nmake-reference.md)