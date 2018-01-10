---
title: "2.5.2 parallel sections 구문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e3a76a950d547effccf0b50fa04799814597bc5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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