---
title: 2.7.2.8 copyprivate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c382348c-c785-45b2-8ee6-a66b76b97f3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c809f297da5059a98915e8055dfe23f45074366f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="2728-copyprivate"></a>2.7.2.8 copyprivate
**copyprivate** 절 다른 구성원에 게 팀의 멤버 중 하나에서 값을 브로드캐스트할 개인 변수를 사용 하는 메커니즘을 제공 합니다. 것 (예를 들어, 각 수준에서 서로 다른 변수를 요구 하는 재귀)에서 어려울 수는 공유 변수를 제공 하는 경우 값에 대 한 공유 변수를 사용 하는 대신 합니다. **copyprivate** 절에 나타날 수는 **단일** 지시문입니다.  
  
 구문은 **copyprivate** 절은 다음과 같습니다.  
  
```  
  
copyprivate(  
variable-list  
)  
  
```  
  
 효과 **copyprivate** 연관 구조화 된 블록으로 실행 된 후 해당 변수 목록에 있는 변수에서 절이 발생는 **단일** 를 만드는 앞의 스레드 중 하나는 팀 장벽 구문이 끝날 때 남은 합니다. 그런 다음의 각 변수에 대해 팀의 다른 모든 스레드는 *변수 목록*, 해당 변수에 되 정의한 (처럼 할당)는 해당 값을 가진 구문이 실행 하는 스레드에서 변수 구조적 블록입니다.  
  
 에 대 한 제한 된 **copyprivate** 절은 다음과 같습니다.  
  
-   에 지정 된 변수는 **copyprivate** 절에 나타나지 않아야는 **개인** 또는 **firstprivate** 동일한 컴퓨터에 대해 절 **단일**지시문입니다.  
  
-   경우는 **단일** 지시문는 **copyprivate** 절에에서가 있으면 동적 병렬 영역 범위에 지정 된 모든 변수는 **copyprivate** 절 이어야 합니다 바깥쪽 컨텍스트에서 private입니다.  
  
-   에 지정 된 변수는 **copyprivate** 절 액세스할 수 있는 명확한 복사 할당 연산자가 있어야 합니다.