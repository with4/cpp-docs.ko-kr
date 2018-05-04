---
title: 여러 대상이 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- makefiles, targets
- multiple targets in NMAKE
- targets, multiple in NMAKE
- NMAKE program, targets
ms.assetid: b609a179-0b9f-4b08-9930-998047588ae0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c1e072b5c831cecabaf1fd63034a0746b3e3419
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="multiple-targets"></a>대상이 여러 개인 경우
NMAKE 각각 별도 설명 블록에는 지정 된 것 처럼 단일 종속성의 여러 대상을 계산 합니다.  
  
 예를 들어,이 중...  
  
```Output  
bounce.exe leap.exe : jump.obj  
   echo Building...  
```  
  
 ... 계산 결과:  
  
```Output  
bounce.exe : jump.obj  
   echo Building...  
leap.exe : jump.obj  
   echo Building...  
```  
  
## <a name="see-also"></a>참고 항목  
 [대상](../build/targets.md)