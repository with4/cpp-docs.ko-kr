---
title: 병렬 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- parallel
dev_langs:
- C++
helpviewer_keywords:
- parallel OpenMP directive
ms.assetid: b8e90073-e85b-4d39-8ed8-0364441794fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e0436dbbc75690d38b5930a491b7058ee095341
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="parallel"></a>parallel
여러 스레드에서 동시에 실행 되는 코드의 병렬 영역을 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#pragma omp parallel [clauses]  
{  
   code_block  
}  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `clause`(선택 사항)  
 0 개 이상의 절입니다.  지 원하는 절을 목록에 대 한 설명 섹션을 참조 **병렬**합니다.  
  
## <a name="remarks"></a>설명  
 **병렬** 지시문 다음 OpenMP 절을 지원 합니다.  
  
-   [copyin](../../../parallel/openmp/reference/copyin.md)  
  
-   [default](../../../parallel/openmp/reference/default-openmp.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [if](../../../parallel/openmp/reference/if-openmp.md)  
  
-   [num_threads](../../../parallel/openmp/reference/num-threads.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
-   [shared](../../../parallel/openmp/reference/shared-openmp.md)  
  
 **병렬** 에 사용할 수는 [섹션](../../../parallel/openmp/reference/sections-openmp.md) 및 [에 대 한](../../../parallel/openmp/reference/for-openmp.md) 지시문입니다.  
  
 자세한 내용은 참조 [2.3 parallel 구문](../../../parallel/openmp/2-3-parallel-construct.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에는 스레드 수를 설정 하 고 병렬 영역을 정의 하는 방법을 보여 줍니다. 기본적으로 스레드 수가 컴퓨터에 논리적 프로세서 수와 같습니다. 예를 들어, 하이퍼 스레딩을 사용 하도록 설정 된 하나의 실제 프로세서 컴퓨터를 설정한 경우은 두 개의 논리 프로세서와 따라서 두 개의 스레드입니다.  
  
```  
// omp_parallel.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(4)  
   {  
      int i = omp_get_thread_num();  
      printf_s("Hello from thread %d\n", i);  
   }  
}  
```  
  
```Output  
Hello from thread 0  
Hello from thread 1  
Hello from thread 2  
Hello from thread 3  
```  
  
## <a name="comment"></a>주석  
 출력의 순서 서로 다른 컴퓨터에서 다를 수 있는 참고 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문](../../../parallel/openmp/reference/openmp-directives.md)