---
title: 2.5.1 parallel for 구문 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a233e7ed-2462-4f7a-9a5d-556ab9f363d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef2732c4f8713466d282346ea240bd3c41886ce0
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687155"
---
# <a name="251-parallel-for-construct"></a>2.5.1 parallel for 구문
**에 대 한 병렬** 지시문이에 대 한 바로 가기는 **병렬** 하나만 포함 된 영역의 **에 대 한** 지시문입니다. 구문은 **에 대 한 병렬** 지시문은 다음과 같습니다.  
  
```  
#pragma omp parallel for [clause[[,] clause] ...] new-linefor-loop  
```  
  
 이 지시문 조건의 모든 절을 사용 하면는 **병렬** 지시문 및 **에 대 한** 지시문을 제외 하 고는 `nowait` 동일한 의미 및 제한 사항으로 절. 의미 체계는 명시적으로 지정 하는 **병렬** 지시문 바로 뒤에 **에 대 한** 지시문입니다.  
  
## <a name="cross-references"></a>교차 참조:  
  
-   **병렬** 지시문 참조 [섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지에 있습니다.  
  
-   **에 대 한** 지시문 참조 [섹션 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) 11 페이지에 있습니다.  
  
-   참조 데이터 특성 절 [2.7.2 데이터 공유 특성 절](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 페이지 25입니다.