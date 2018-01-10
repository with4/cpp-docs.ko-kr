---
title: "의도 하지 않은 종속성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dependencies, side effects
- NMAKE program, dependents
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f595099d2a71c948c769adf7f7eafcbc373f3146
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="dependency-side-effects"></a>종속 줄의 부수적 효과
서로 다른 위치에 두 개의 종속 줄에는 콜론 (:)으로 지정 된 대상 및 줄 중 하나에 다음 명령에 표시 하는 경우 인접 하거나 결합 된 마치 NMAKE 종속성을 해석 합니다. 명령이 나타나지 대신 종속성 하나의 설명 블록에 속해 있으며 다른 종속성이 있는 지정 된 명령을 실행 한다고 가정 된 종속성에 대 한 유추 규칙을 호출 하지는 않습니다. 예를 들어이 규칙의 설정.  
  
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
  
 이 적용 되지 않습니다 경우 두 개의 콜론 (`::`) 사용 됩니다. 예를 들어이 규칙의 설정.  
  
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