---
title: 4.1 OMP_SCHEDULE | Microsoft Docs
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
ms.assetid: d0dce411-2351-4ee9-a1cc-c0322a58b65c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 330e5ea576e3cd779a7c17c21d00b6459f5e7043
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2018
---
# <a name="41-ompschedule"></a>4.1 OMP_SCHEDULE
**OMP_SCHEDULE** 에 적용 됩니다 **에 대 한** 및 **에 대 한 병렬** 일정 유형을 가진 지시문 **런타임**합니다. 인식 된 일정 유형 중 하나로 및 선택적를이 환경 변수를 설정 하 여 런타임 시 이러한 모든 루프에 대 한 일정 유형 및 청크 크기를 설정할 수 있습니다 *chunk_size*합니다.  
  
 에 대 한 **에 대 한** 및 **에 대 한 병렬** 이외의 일정 유형을 포함 하는 지시문 **런타임**, **OMP_SCHEDULE** 는 무시 됩니다. 이 환경 변수에 대 한 기본값은 구현 시 정의 합니다. 경우 선택적 *chunk_size* 설정 되 면 값은 양수 여야 합니다. 경우 *chunk_size* 값이 1 가정를 설정 하지 않으면의 경우를 제외 하 고는 **정적** 일정. 에 대 한는 **정적** 일정을 기본 청크 크기는 루프 반복 공간 루프에 적용 되는 스레드 수로 나눈 값으로 설정 되어 있습니다.  
  
 예제:  
  
```  
setenv OMP_SCHEDULE "guided,4"  
setenv OMP_SCHEDULE "dynamic"  
```  
  
## <a name="cross-references"></a>교차 참조:  
  
-   **에 대 한** 지시문 참조 [섹션 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) 11 페이지에 있습니다.  
  
-   **에 대 한 병렬** 지시문 참조 [섹션 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) 페이지 16입니다.