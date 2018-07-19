---
title: 2.5.2 parallel sections 구문 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6f7a84e322cb273733c6a724ee2563928df8362
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689482"
---
# <a name="252-parallel-sections-construct"></a>2.5.2 parallel sections 구문
**섹션 병렬** 지시어를 지정 하기 위한 바로 가기 형식을 제공는 **병렬** 하나만 포함 된 영역 **섹션** 지시문입니다. 의미 체계는 명시적으로 지정 하는 **병렬** 지시문 바로 뒤에 **섹션** 지시문입니다. 구문은 **섹션 병렬** 지시문은 다음과 같습니다.  
  
```  
#pragma omp parallel sections  [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-linestructured-block  ]  
   ...  
}  
```  
  
 *절* 수락한 절 중 하나일 수 있습니다는 **병렬** 및 **섹션** 지시문을 제외 하 고는 **nowait** 절.  
  
## <a name="cross-references"></a>교차 참조:  
  
-   **병렬** 지시문 참조 [섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지에 있습니다.  
  
-   **섹션** 지시문 참조 [섹션 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) 14 페이지.