---
title: "배치 모드 규칙 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- inference rules in NMAKE
- NMAKE program, inference rules
- batch-mode inference rules in NMAKE
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0faeb66f728c826f8d499ee6f033cecc7250a5b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="batch-mode-rules"></a>일괄 처리 모드 규칙
```  
{frompath}.fromext{topath}.toext::  
   commands  
```  
  
 일괄 처리 모드 유추 규칙 N 명령을이 유추 규칙을 통해 이동 하는 경우 한 번만 호출의 유추 규칙을 제공 합니다. 일괄 처리 모드 유추 규칙 없이 N 명령을를 호출 해야 합니다. N은 유추 규칙을 트리거하는 종속 항목 수입니다.  
  
 일괄 처리 모드 유추 규칙을 포함 하는 메이크파일 NMAKE 버전 1.62 이상을 사용 해야 합니다. NMAKE 버전을 확인 하려면 1.62 이상을 사용할 수 있는 _NMAKE_VER 매크로와 NMAKE 버전 실행 합니다. 이 매크로 Visual c + + 제품 버전을 나타내는 문자열을 반환 합니다.  
  
 표준 유추 규칙에서만 구문 차이점은 일괄 처리 모드 유추 규칙 이중 콜론 (:)으로 종료 됩니다.  
  
> [!NOTE]
>  호출 되는 도구는 여러 파일을 처리할 수 있어야 합니다. 일괄 처리 모드 유추 규칙을 사용 해야 `$<` 종속 파일에 액세스 매크로로 합니다.  
  
 일괄 처리 모드 유추 규칙 빌드 프로세스를 가속화할 수 있습니다. 되므로 더 빠르게 일괄 처리에 컴파일러에 파일을 제공 하 컴파일러 드라이버가 한 번만 호출 됩니다. 예를 들어, C 및 c + + 컴파일러가 성능이 프로세스 중에 상주 하기 때문에 파일 집합을 처리할 때 더 잘 수행 합니다.  
  
 다음 예에서는 일괄 처리 모드 유추 규칙을 사용 하는 방법을 보여 줍니다.  
  
```  
#  
# sample makefile to illustrate batch-mode inference rules  
#  
O = .  
S = .  
Objs = $O/foo1.obj $O/foo2.obj $O/foo2.obj $O/foo3.obj $O/foo4.obj  
CFLAGS = -nologo  
  
all : $(Objs)  
  
!ifdef NOBatch  
{$S}.cpp{$O}.obj:  
!else  
{$S}.cpp{$O}.obj::  
!endif  
   $(CC) $(CFLAGS) -Fd$O\ -c $<  
  
$(Objs) :  
  
#end of makefile  
```  
  
 NMAKE 일괄 처리 모드 유추 규칙 없이 다음과 같은 출력을 생성합니다.  
  
```  
E:\tmp> nmake -f test.mak -a NOBatch=1  
  
Microsoft (R) Program Maintenance Utility   Version 7.00.0000  
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.  
        cl -nologo -Fd.\ -c .\foo1.cpp  
foo1.cpp  
        cl -nologo -Fd.\ -c .\foo2.cpp  
foo2.cpp  
        cl -nologo -Fd.\ -c .\foo3.cpp  
foo3.cpp  
        cl -nologo -Fd.\ -c .\foo4.cpp  
foo4.cpp  
```  
  
 NMAKE는 일괄 처리 모드 유추 규칙은 다음 결과 생성합니다.  
  
```  
E:\tmp> nmake -f test.mak -a  
  
Microsoft (R) Program Maintenance Utility   Version 7.00.0000  
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.  
  
        cl -nologo -Fd.\ -c .\foo1.cpp .\foo2.cpp .\foo3.cpp .\foo4.cpp  
foo1.cpp  
foo2.cpp  
foo3.cpp  
foo4.cpp  
Generating Code...  
```  
  
## <a name="see-also"></a>참고 항목  
 [유추 규칙](../build/inference-rules.md)