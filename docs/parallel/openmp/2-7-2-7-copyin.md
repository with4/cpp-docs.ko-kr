---
title: 2.7.2.7 copyin | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ee711bfb24e7a2a1cbada1a7e01a243e204f4a8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689378"
---
# <a name="2727-copyin"></a>2.7.2.7 copyin
**copyin** 절에 동일한 값을 할당 하는 메커니즘을 제공 **threadprivate** 병렬 영역을 실행 하는 팀에서 각 스레드에 대 한 변수입니다. 에 지정 된 각 변수에 대해는 **copyin** 병렬 영역 맨 앞에 스레드 전용 복사본에 할당 하 여 마치 절, 팀의 마스터 스레드에의 변수 값을 복사 합니다. 구문은 **copyin** 절은 다음과 같습니다.  
  
```  
  
copyin(  
variable-list  
)  
  
```  
  
 시의 제한 된 **copyin** 절은 다음과 같습니다.  
  
-   에 지정 된 변수는 **copyin** 절 액세스 가능 하며 명확한 복사 할당 연산자가 있어야 합니다.  
  
-   에 지정 된 변수는 **copyin** 절 이어야 합니다는 **threadprivate** 변수입니다.