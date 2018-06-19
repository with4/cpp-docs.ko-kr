---
title: 단일 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- Single
dev_langs:
- C++
helpviewer_keywords:
- single OpenMP directive
ms.assetid: 85cf94fb-cb9c-4d82-8609-adffa9f552e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6dd5349331ac23998511a8f1b838d2cd13b01998
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691861"
---
# <a name="single"></a>단일
코드의 섹션을 마스터 스레드에 반드시 단일 스레드에서 실행할지 지정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
#pragma omp single [clauses]   
{  
   code_block   
}  
```  
  
#### <a name="parameters"></a>매개 변수  
 `clause`(선택 사항)  
 0 개 이상의 절입니다. 지 원하는 절을 목록에 대 한 설명 섹션을 참조 **단일**합니다.  
  
## <a name="remarks"></a>설명  
 **단일** 지시문 다음 OpenMP 절을 지원 합니다.  
  
-   [copyprivate](../../../parallel/openmp/reference/copyprivate.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
 [마스터](../../../parallel/openmp/reference/master.md) 지시문을 사용 하면 코드의 섹션 마스터 스레드에 대해서만 실행 않아야 함을 지정할 수 있습니다.  
  
 자세한 내용은 참조 [2.4.3 single 생성](../../../parallel/openmp/2-4-3-single-construct.md)합니다.  
  
## <a name="example"></a>예제  
  
```  
// omp_single.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(2)  
   {  
      #pragma omp single  
      // Only a single thread can read the input.  
      printf_s("read input\n");  
  
      // Multiple threads in the team compute the results.  
      printf_s("compute results\n");  
  
      #pragma omp single  
      // Only a single thread can write the output.  
      printf_s("write output\n");  
    }  
}  
```  
  
```Output  
read input  
compute results  
compute results  
write output  
```  
  
## <a name="see-also"></a>참고 항목  
 [지시문](../../../parallel/openmp/reference/openmp-directives.md)