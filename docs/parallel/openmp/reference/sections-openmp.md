---
title: 섹션 (OpenMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- section
- SECTIONS
dev_langs:
- C++
helpviewer_keywords:
- sections OpenMP directive
ms.assetid: 4cd1d776-e198-470e-930a-01fb0ab0a0bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60bc94685a7e6128e22cc3545ae8702abe6d472e
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692079"
---
# <a name="sections-openmp"></a>sections (OpenMP)
모든 스레드가에서 나눌 수 있는 코드 섹션을 식별 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#pragma omp [parallel] sections [clauses]  
{  
   #pragma omp section  
   {  
      code_block   
   }   
}  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `clause`(선택 사항)  
 0 개 이상의 절입니다. 지 원하는 절을 목록에 대 한 설명 섹션을 참조 **섹션**합니다.  
  
## <a name="remarks"></a>설명  
 **섹션** 지시문에는 0 또는 그 이상 포함 될 수 있습니다 **섹션** 지시문입니다.  
  
 **섹션** 지시문 다음 OpenMP 절을 지원 합니다.  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [lastprivate](../../../parallel/openmp/reference/lastprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
 경우 **병렬** 도 지정 `clause` 모든 절에 허용 될 수는 **병렬** 또는 **섹션** 지시문을 제외 하 고 `nowait`합니다.  
  
 자세한 내용은 참조 [2.4.2 sections 구문](../../../parallel/openmp/2-4-2-sections-construct.md)합니다.  
  
## <a name="example"></a>예제  
  
```  
// omp_sections.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
    #pragma omp parallel sections num_threads(4)  
    {  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
        #pragma omp section  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
    }  
}  
```  
  
```Output  
Hello from thread 0  
Hello from thread 0  
```  
  
## <a name="see-also"></a>참고 항목  
 [지시문](../../../parallel/openmp/reference/openmp-directives.md)