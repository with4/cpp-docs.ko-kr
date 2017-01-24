---
title: "대상이 여러 개인 경우 | Microsoft Docs"
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
  - "메이크파일에 대상"
  - "NMAKE의 여러 대상"
  - "nmake의 다중 항목 대상"
  - "NMAKE 프로그램을 대상으로"
ms.assetid: b609a179-0b9f-4b08-9930-998047588ae0
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 대상이 여러 개인 경우
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE 각각 별도 설명 블록에는 지정 된 것 처럼 단일 종속성의 여러 대상을 계산 합니다.  
  
 예를 들어,이 중...  
  
```Output  
bounce.exe leap.exe : jump.obj  
   echo Building...  
```  
  
 .. 계산 결과:  
  
```Output  
bounce.exe : jump.obj  
   echo Building...  
leap.exe : jump.obj  
   echo Building...  
```  
  
## <a name="see-also"></a>참고 항목  
 [대상](../build/targets.md)