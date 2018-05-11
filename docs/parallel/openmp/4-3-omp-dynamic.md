---
title: 4.3 OMP_DYNAMIC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a15edefb-1f85-4f06-a427-beb3cfc4434f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f376fe639d9bca58b6e2bd55fd081b88921a7342
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="43-ompdynamic"></a>4.3 OMP_DYNAMIC
**OMP_DYNAMIC** 환경 변수 사용 하거나 동적인 조절을 명시적으로 사용 하거나는 를호출하여사용하지않도록설정하지않는한병렬영역의실행에사용할수있는스레드수의동적조정을사용하지않도록설정**omp_set_dynamic** 라이브러리 루틴입니다. 변수 값 이어야 합니다 **TRUE** 또는 **FALSE**합니다.  
  
 경우 설정 **TRUE**, 병렬 영역을 실행 하는 데 사용 되는 스레드 수는 시스템 리소스를 최대한 활용 하려면 런타임 환경에 의해 조정 될 수 있습니다.  경우 설정 **FALSE**, 이상을 사용할 수 없습니다. 기본 상태는 구현 정의 합니다.  
  
 예제:  
  
```  
setenv OMP_DYNAMIC TRUE  
```  
  
## <a name="cross-references"></a>교차 참조:  
  
-   병렬 영역에 대 한 자세한 내용은 참조 하십시오. [섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지에 있습니다.  
  
-   **omp_set_dynamic** 함수, 참조 [섹션 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 페이지.