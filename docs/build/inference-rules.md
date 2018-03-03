---
title: "유추 규칙 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- NMAKE program, inference rules
ms.assetid: caff320f-fb07-4eea-80c3-a6a2133a8492
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 932aad860cd2b78208857ca7b028e35cd96d481e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="inference-rules"></a>유추 규칙
유추 규칙 대상을 업데이트 하 고 대상에 대 한 종속 항목을 유추 하는 명령을 제공 합니다. 확장이 유추 규칙에 일치 하는 단일 대상 있고 종속 기본 이름은 동일 합니다. 유추 규칙은 사용자 지정 또는 미리 정의 된; 미리 정의 된 규칙을 재정의할 수 있습니다.  
  
 오래 된 종속성에 더 명령이 있고 [합니다. 접미사](../build/dot-directives.md) NMAKE 현재 또는 지정 된 디렉터리에 파일 대상과 기존의 일치 하는 규칙을 사용 하 여 종속 항목의 확장명을 포함 합니다. 하나 이상의 규칙 기존 파일과 일치 하는 경우는 **합니다. 접미사** 목록을 사용 하는 결정; 우선 순위 목록 왼쪽에서 오른쪽으로 이어집니다. 종속 파일이 존재 하지 않는 다른 설명 블록에 나열 되지 않은 경우 유추 규칙에서에서 만들 수 누락 된 종속 동일한 기본 이름 가진 다른 파일이 있습니다. 설명 블록의 대상에 없는 종속 파일이 나 명령이 있으면, 유추 규칙 대상을 업데이트할 수 있습니다. 유추 규칙 설명 블록이 없는 경우에 명령줄 대상을 빌드할 수 있습니다. 명시적 종속 파일이 지정 하는 경우에 NMAKE 유추 된 종속에 대 한 규칙을 호출할 수 있습니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
 [규칙 정의](../build/defining-a-rule.md)  
  
 [배치 모드 규칙](../build/batch-mode-rules.md)  
  
 [미리 정의 된 규칙](../build/predefined-rules.md)  
  
 [유추 된 종속 파일과 규칙](../build/inferred-dependents-and-rules.md)  
  
 [유추 규칙의 우선 순위](../build/precedence-in-inference-rules.md)  
  
## <a name="see-also"></a>참고 항목  
 [NMAKE 참조](../build/nmake-reference.md)