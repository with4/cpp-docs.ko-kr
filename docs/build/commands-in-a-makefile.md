---
title: "메이크파일의 명령 | Microsoft Docs"
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
  - "명령, 메이크파일"
ms.assetid: 8085517e-42f4-493b-b8f8-44311fc08c64
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 메이크파일의 명령
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

설명 불록이나 유추 규칙은 종속 행이 오래된 경우 실행할 명령 블록을 지정합니다.  \/S, **.SILENT**, **\!CMDSWITCHES** 또는 @를 사용하지 않은 경우 NMAKE는 각 명령을 표시한 후 실행합니다.  설명 블록 뒤에 명령 블록이 오지 않으면 NMAKE가 일치하는 유추 규칙을 찾습니다.  
  
 명령 블록에는 하나 이상의 명령이 포함되어 있으며 각 명령은 한 줄에 하나씩 지정됩니다.  종속 줄 과 명령 블록 또는 규칙과 명령 블록 사이에 빈 줄을 사용할 수 없습니다.  그러나, 공백이나 탭만 포함된 줄은 표시할 수 있습니다. 이 줄은 null 명령으로 해석되므로 오류가 발생하지 않습니다.  빈 줄은 명령줄 사이에만 사용할 수 있습니다.  
  
 명령줄은 하나 이상의 공백이나 탭으로 시작됩니다.  줄 바꿈 문자 앞에 오는 백슬래시\( \\ \)는 명령에서 공백으로 해석되므로 다음 줄에서 명령을 계속하려면 줄 끝에 백슬래시를 사용합니다.  백슬래시 뒤에 공백이나 탭을 비롯한 다른 문자가 오는 경우 NMAKE는 백슬래시를 문자 그대로 해석합니다.  
  
 앞에 세미콜론\(;\)이 있는 명령은 뒤에 명령 블록이 있는지 여부에 관계 없이 종속 줄이나 유추 규칙에 표시할 수 있습니다.  
  
```  
project.obj : project.c project.h ; cl /c project.c  
```  
  
## 추가 정보  
 [명령 한정자](../build/command-modifiers.md)  
  
 [파일 이름 부분 구문](../build/filename-parts-syntax.md)  
  
 [메이크파일의 인라인 파일](../build/inline-files-in-a-makefile.md)  
  
## 참고 항목  
 [NMAKE 참조](../build/nmake-reference.md)