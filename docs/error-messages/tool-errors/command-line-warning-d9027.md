---
title: "명령줄 경고 D9027 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D9027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9027"
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 명령줄 경고 D9027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\<filename\> 소스 파일을 무시합니다.  
  
 CL.exe가 입력 소스 파일을 무시합니다.  
  
 이 경고는 \/Fo 옵션과 \/c 옵션을 포함하는 명령줄의 출력 파일 이름 사이에 공백이 있는 경우에 발생할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
cl /c /Fo output.obj input.c   
```  
  
 \/Fo와 `output.obj,` 사이에 공백이 있으므로 CL.exe는 `output.obj`를 입력 파일의 이름으로 가져옵니다.  이 문제를 해결하려면 다음과 같이 공백을 제거하십시오.  
  
```  
cl /c /Fooutput.obj input.c   
```