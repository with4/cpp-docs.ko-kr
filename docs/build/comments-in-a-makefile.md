---
title: 메이크파일의 주석 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- makefiles, comments
ms.assetid: 76fd9e3d-5966-47f4-a091-c9e80b232b49
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e404f3fffd0176e63a2df89d4d879bfba07f7093
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366785"
---
# <a name="comments-in-a-makefile"></a>메이크파일의 주석
앞에 숫자 기호를 사용 하 여 주석을 (#). NMAKE 다음 줄 바꿈 문자로 숫자 기호에서 텍스트를 무시합니다. 예를 들면 다음과 같습니다.  
  
```  
# Comment on line by itself  
OPTIONS = /MAP  # Comment on macro definition line  
  
all.exe : one.obj two.obj  # Comment on dependency line  
    link one.obj two.obj  
# Comment in commands block  
#   copy *.obj \objects  # Command turned into comment  
    copy one.exe \release  
  
.obj.exe:  # Comment on inference rule line  
    link $<  
  
my.exe : my.obj ; link my.obj  # Err: cannot comment this  
 # Error: # must be the first character  
.obj.exe: ; link $<  # Error: cannot comment this  
```  
  
 리터럴 숫자 기호를 지정 하려면 앞에 캐럿 (**^**), 다음과 같습니다.  
  
```  
DEF = ^#define  #Macro for a C preprocessing directive  
```  
  
## <a name="see-also"></a>참고 항목  
 [메이크파일의 내용](../build/contents-of-a-makefile.md)