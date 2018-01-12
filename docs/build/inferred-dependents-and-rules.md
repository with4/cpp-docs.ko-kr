---
title: "종속 파일과 규칙 유추 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- rules, inferred
- inferred dependents in NMAKE
- inferred rules in NMAKE
- dependents, inferred
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fe7c49607f466d8fd1d333883414b24d7837432b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="inferred-dependents-and-rules"></a>유추된 종속 파일과 규칙
NMAKE 유추 해당 규칙이 있는 경우 대상에 대해 유추 된 종속을 가정 합니다. 규칙을 적용 하는 경우 됩니다.  
  
-   *toext* 대상의 확장명과 일치 합니다.  
  
-   *fromext* 일치 대상의 기본 이름 및를 포함 하는 파일의 확장명 현재 또는 지정 된 디렉터리에 있습니다.  
  
-   *fromext* 중인 [합니다. 접미사](../build/dot-directives.md); 다른 *fromext* 일치 규칙에는 더 높은 **합니다. 접미사** 우선 순위입니다.  
  
-   명시적 종속 없는 파일에 더 높은 **합니다. 접미사** 우선 순위입니다.  
  
 유추 된 종속 파일에 예기치 않은 파생 작업이 발생할 수 있습니다. NMAKE의 대상의 설명 블록 명령이 포함 된 경우 규칙에 명령 대신 명령을 실행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [유추 규칙](../build/inference-rules.md)