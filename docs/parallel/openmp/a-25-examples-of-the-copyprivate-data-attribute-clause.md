---
title: "A.25   Examples of the copyprivate Data Attribute Clause | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 7b1cb6a5-5691-4b95-b3ac-d7543ede6405
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.25   Examples of the copyprivate Data Attribute Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**예제 1:** 는 `copyprivate` 절 \([2.7.2.8 섹션](../../parallel/openmp/2-7-2-8-copyprivate.md) 32 페이지에\) 브로드캐스트 단일 스레드가 직접 다른 스레드는 개인 변수의 모든 인스턴스를 통해 얻은 값을 사용할 수 있습니다.  
  
```  
float x, y;  
#pragma omp threadprivate(x, y)  
  
void init( )   
{  
    float a;  
    float b;  
  
    #pragma omp single copyprivate(a,b,x,y)  
    {  
        get_values(a,b,x,y);  
    }  
  
    use_values(a, b, x, y);  
}  
```  
  
 일상적인 경우  *init* 라고 하면 직렬 영역에서 동작의 지시문의 존재가 영향을 받습니다.  호출 하면 해당  *get\_values* 루틴 한 스레드에 의해 실행 된, 스레드 구문 지정 개인 개체까지 나갈  *는*,  *b*,  *x*, 및  *y* 모든 스레드를 읽은 값으로 정의 될.  
  
 **예제 2:** 이전 예제와 달리 읽기 마스터 스레드 예를 들어 특정 스레드에 의해 수행 해야 한다고 가정 합니다.  이 경우에 `copyprivate` 절 직접 브로드캐스트에 사용할 수 없습니다 있지만 임시 공유 객체 액세스를 사용할 수 있습니다.  
  
```  
float read_next( )   
{  
    float * tmp;  
    float return_val;  
  
    #pragma omp single copyprivate(tmp)  
    {  
        tmp = (float *) malloc(sizeof(float));  
    }  
  
    #pragma omp master  
    {  
        get_float( tmp );  
    }  
  
    #pragma omp barrier  
    return_val = *tmp;  
    #pragma omp barrier  
  
    #pragma omp single  
    {  
       free(tmp);  
    }  
  
    return return_val;  
}  
```  
  
 **예제 3:** 입력 하기 전에 병렬 영역 내부에서는 필요한 잠금 개체 수를 쉽게 확인할 수 있다는 가정 합니다.  `copyprivate` 절을 사용 하 여 액세스 해당 병렬 영역 내부에 할당 된 공유 잠금 개체를 제공할 수 있습니다.  
  
```  
#include <omp.h>  
  
omp_lock_t *new_lock()  
{  
    omp_lock_t *lock_ptr;  
  
    #pragma omp single copyprivate(lock_ptr)  
    {  
        lock_ptr = (omp_lock_t *) malloc(sizeof(omp_lock_t));  
        omp_init_lock( lock_ptr );  
    }  
  
    return lock_ptr;  
}  
```