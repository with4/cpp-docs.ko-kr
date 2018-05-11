---
title: omp_set_nested | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_nested
dev_langs:
- C++
helpviewer_keywords:
- omp_set_nested OpenMP function
ms.assetid: fa1cb08c-7b8b-42c9-8654-2c33dcffb5b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6539167b936efdc4c9f407cd951c9c582b0a138
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="ompsetnested"></a>omp_set_nested
중첩 된 병렬 처리가 가능 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void omp_set_nested(  
   int val  
);  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `val`  
 0이 아니면 중첩 된 병렬 처리가 가능 합니다. 0 이면 중첩 된 병렬 처리를 해제 합니다.  
  
## <a name="remarks"></a>설명  
 OMP 중첩 된 병렬 처리 수준으로 설정할 수 있습니다 `omp_set_nested`, 하거나 설정 하는 [OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md) 환경 변수입니다.  
  
 에 대 한 설정을 `omp_set_nested` 의 설정을 재정의 합니다는 `OMP_NESTED` 환경 변수입니다.  
  
 를 사용 하는 경우에 환경 변수 병렬 영역을 중첩할 때 스레드 수가 기하급수적으로 증가 하기 때문에 그렇지 않으면 operational 프로그램에 중단할 수 있습니다.  예를 들어 일반적 스레드 수를 4로 설정 하는 OMP 스레드의 수와 6 회를 재귀적 4096 (6의 4)이 필요 하다는 함수, 스레드 수의 프로세서 수를 초과 하는 경우 응용 프로그램의 성능이 저하 됩니다. 이 한 가지 예외는 I/O 바운드 응용 프로그램 것입니다.  
  
 사용 하 여 [omp_get_nested](../../../parallel/openmp/reference/omp-get-nested.md) 의 현재 설정을 표시 하려면 `omp_set_nested`합니다.  
  
 자세한 내용은 참조 [3.1.9 omp_set_nested 함수](../../../parallel/openmp/3-1-9-omp-set-nested-function.md)합니다.  
  
## <a name="example"></a>예제  
  
```  
// omp_set_nested.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    omp_set_nested(1);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_nested( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_nested( ));  
        }  
}  
```  
  
```Output  
1  
1  
```  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../../parallel/openmp/reference/openmp-functions.md)