---
title: "일괄 처리 모드 규칙 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NMAKE의 일괄 처리 모드 유추 규칙"
  - "NMAKE의 유추 규칙"
  - "NMAKE 프로그램, 유추 규칙"
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 일괄 처리 모드 규칙
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

```  
{frompath}.fromext{topath}.toext::  
   commands  
```  
  
 일괄 처리 모드 유추 규칙은 N 개의 명령에 유추 규칙이 적용되는 경우 이 유추 규칙을 한 번만 호출합니다.  일괄 처리 모드 유추 규칙을 사용하지 않는 경우 N 개의 명령을 호출해야 합니다.  N은 유추 규칙을 트리거하는 종속 파일의 수입니다.  
  
 일괄 처리 모드 유추 규칙이 포함된 메이크파일은 NMAKE 버전 1.62 이상을 사용해야 합니다.  NMAKE 버전을 확인하려면 NMAKE 버전 1.62 이상에서 사용할 수 있는 \_NMAKE\_VER 매크로를 실행합니다.  이 매크로는 Visual C\+\+ 제품 버전을 나타내는 문자열을 반환합니다.  
  
 일괄 처리 모드 유추 규칙 구문이 표준 유추 규칙과 다른 점은 이중 콜론\(::\)으로 끝난다는 것입니다.  
  
> [!NOTE]
>  호출되는 도구는 여러 개의 파일을 처리할 수 있어야 합니다.  일괄 처리 모드 유추 규칙은 `$<`를 매크로로 사용하여 종속 파일에 액세스해야 합니다.  
  
 일괄 처리 모드 유추 규칙은 빌드 프로세스를 단축할 수 있습니다.  컴파일러에 파일을 일괄 공급하면 컴파일러 드라이버가 한 번만 호출되므로 프로세스가 빨라집니다.  예를 들어, C와 C\+\+ 컴파일러는 파일 세트를 처리하는 경우 성능이 향상됩니다. 프로세스 수행 중에 컴파일러가 메모리에 상주할 수 있기 때문입니다.  
  
 다음 예제는 일괄 처리 모드 유추 규칙을 사용하는 방법을 보여 줍니다.  
  
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
  
 일괄 처리 모드 유추 규칙을 사용하지 않는 경우 NMAKE에서 생성하는 다음과 같이 출력됩니다.  
  
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
  
 일괄 처리 모드 유추 규칙을 사용하는 경우 NMAKE에서 생성하는 다음과 같이 출력됩니다.  
  
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
  
## 참고 항목  
 [유추 규칙](../build/inference-rules.md)