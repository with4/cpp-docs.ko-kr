---
title: "메이크파일의 주석 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메이크파일, 주석"
ms.assetid: 76fd9e3d-5966-47f4-a091-c9e80b232b49
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 메이크파일의 주석
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

주석 앞에는 숫자 기호\(\#\)를 사용합니다.  NMAKE는 숫자 기호와 줄 바꿈 문자 사이의 텍스트를 무시합니다.  예를 들면 다음과 같습니다.  
  
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
  
 리터럴 숫자 기호를 지정하려면 다음과 같이 숫자 표시 앞에 캐럿\(**^**\)을 사용합니다.  
  
```  
DEF = ^#define  #Macro for a C preprocessing directive  
```  
  
## 참고 항목  
 [메이크파일의 내용](../build/contents-of-a-makefile.md)