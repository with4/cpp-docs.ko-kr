---
title: "누적되는 종속 줄 | Microsoft Docs"
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
  - "누적 종속성"
  - "NMAKE의 누적 종속성"
  - "종속성"
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 누적되는 종속 줄
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대상이 반복 되는 경우 종속성 설명 블록에 누적 됩니다.  
  
 예를 들어이 규칙 집합에  
  
```Output  
bounce.exe : jump.obj  
bounce.exe : up.obj  
   echo Building bounce.exe...  
```  
  
 이 평가 됩니다.  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 단일 설명 블록에 여러 개의 종속 줄의 여러 대상에는 각각 별도 설명 블록에 지정 된 마지막 종속성 줄에 포함 된 대상만 명령 블록을 사용 하지 않는 경우 처럼 평가 됩니다. NMAKE 유추 규칙을 사용 하 여 이러한 대상에 대 한 하려고 시도 합니다.  
  
 예를 들어이 규칙 집합에  
  
```Output  
leap.exe bounce.exe : jump.obj  
bounce.exe climb.exe : up.obj  
   echo Building bounce.exe...  
```  
  
 이 평가 됩니다.  
  
```Output  
  
leap.exe : jump.obj  
# invokes an inference rule  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
climb.exe : up.obj  
   echo Building bounce.exe...  
```  
  
## <a name="see-also"></a>참고 항목  
 [대상](../build/targets.md)