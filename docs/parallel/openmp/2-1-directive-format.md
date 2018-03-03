---
title: "2.1 지시문 형식 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 918b6445-d35e-4176-9565-b045be941b4d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c3ff4e0078ffd086ce3b62d8927184188f0ebdd8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="21-directive-format"></a>2.1 지시문 형식
OpenMP 지시문의 구문은 문법을 지정 공식적으로 [부록 C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md), 다음과 같이 비공식적 및:  
  
```  
#pragma omp directive-name  [clause[ [,] clause]...] new-line  
```  
  
 각 지시문으로 시작 **#pragma omp**를 같은 이름의 다른 (openmp-OpenMP 또는 공급 업체 확장) pragma 지시문의 충돌을 방지 합니다. 지시문의 나머지 부분에서는 C 및 c + + 표준 컴파일러 지시문에 대 한 규칙을 따릅니다. 특히, 공백은 사용할 수 앞과 뒤는  **#** , 지시문에서 단어를 구분 하 여 공백을 경우에 따라 사용 해야 합니다. 전처리 토큰 뒤의 **#pragma omp** 매크로 대체 영향을 받습니다.  
  
 지시문 대/소문자를 구분 하지 않습니다. 지시문에 절이 표시 되는 순서는 중요 하지 않습니다. 각 절에 대 한 설명을에 나열 된 제한에 따라 필요에 따라 지시문에 절을 반복 될 수 있습니다. 경우 *변수 목록* 만 변수를 지정 해야 하는 절에 나타납니다. 하나의 *지시문 이름* 지시문에 따라 지정할 수 있습니다.  예를 들어 다음 지시문은 사용할 수 없습니다.  
  
```  
/* ERROR - multiple directive names not allowed */  
#pragma omp parallel barrier  
```  
  
 OpenMP 지시문 대상에 대 한 최대 하나의 이어지는, 구조화 된 블록 이어야 합니다.