---
title: "종속 줄의 부수적 효과 | Microsoft Docs"
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
  - "종속성을 의도 하지 않은 결과"
  - "NMAKE 프로그램, 종속 항목"
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 종속 줄의 부수적 효과
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다른 위치에 두 개의 종속 줄에는 콜론 (:)으로 대상이 지정 및 줄 중 하나에 다음 명령에 표시 하는 경우 인접 하거나 결합 하는 경우에 따라 NMAKE 종속성을 해석 합니다. 대신 종속성 하나의 설명 블록에 속해 있으며 다른 종속성이 있는 지정 된 명령을 실행 한다고 가정 했지만 명령이 나타나지 않은 종속성에 대 한 유추 규칙을 호출 하지는 않습니다. 예를 들어이 규칙의 설정.  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
```  
  
 이 평가 됩니다.  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 이 적용 되지 않습니다 경우 이중 콜론 (`::`) 사용 됩니다. 예를 들어이 규칙의 설정.  
  
```Output  
bounce.exe :: jump.obj  
   echo Building bounce.exe...  
  
bounce.exe :: up.obj  
```  
  
 이 평가 됩니다.  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
# invokes an inference rule  
```  
  
## <a name="see-also"></a>참고 항목  
 [대상](../build/targets.md)