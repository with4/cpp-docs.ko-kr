---
title: "2.4.2 sections 구문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6e5b755e95e9bbbb78d6ab13cd09732f9c9aee3d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="242-sections-construct"></a>2.4.2 sections 구문
**섹션** 지시문 팀에 스레드 간에 나눠집니다 않는 구문이의 집합을 지정 하는 noniterative 작업 공유 구문을 식별 합니다. 각 섹션은 팀의 스레드에 의해 한 번만 실행 됩니다. 구문은 **섹션** 지시문은 다음과 같습니다.  
  
```  
#pragma omp sections [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-linestructured-block ]  
...  
}  
```  
  
 절은 다음 중 하나입니다.  
  
 **개인 (** *변수 목록* **)**  
  
 **firstprivate (** *변수 목록* **)**  
  
 **lastprivate (** *변수 목록* **)**  
  
 **감소 (** *연산자* **:***변수 목록* **)**   
  
 **nowait**  
  
 각 섹션 앞는 **섹션** 지시문을 사용 하지만 **섹션** 지시문은 첫 번째 섹션에 대 한 선택 사항입니다. **섹션** 어휘 범위 내에서 지시문이 나타나야 합니다.는 **섹션** 지시문입니다. 끝에 암시적 장벽은는 **섹션** 하지 않는 경우 만들는 **nowait** 지정 됩니다.  
  
 에 대 한 제한 된 **섹션** 지시문은 다음과 같습니다.  
  
-   A **섹션** 지시문의 어휘 범위 외부에 나타나지 않아야는 **섹션** 지시문입니다.  
  
-   단일 **nowait** 절에 나타날 수 있습니다는 **섹션** 지시문입니다.  
  
## <a name="cross-references"></a>교차 참조:  
  
-   **개인**, **firstprivate**, **lastprivate**, 및 **감소** 절에서 참조 [섹션 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 25 페이지.