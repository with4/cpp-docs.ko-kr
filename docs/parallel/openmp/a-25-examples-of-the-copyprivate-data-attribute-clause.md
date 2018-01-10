---
title: "Copyprivate 데이터 특성 절의 A.25 예 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 7b1cb6a5-5691-4b95-b3ac-d7543ede6405
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7cdf7598e00bab72966fe79454567b0a59dcbaae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="a25---examples-of-the-copyprivate-data-attribute-clause"></a>A.25   copyprivate 데이터 특성 절 예제
**예제 1:** 는 `copyprivate` 절 ([2.7.2.8 섹션](../../parallel/openmp/2-7-2-8-copyprivate.md) 페이지 32) 직접 다른 스레드에서 개인 변수의 모든 인스턴스에 단일 스레드에서 획득 값 브로드캐스트에 사용할 수 있습니다.  
  
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
  
 일상적인 경우 *init* 라고 직렬 영역에서 해당 동작의 영향을 받지 지시문의 현재 상태입니다. 호출 후의 *get_values* 루틴 한 스레드에 의해 실행 된 스레드가 없습니다로 지정 된 private 개체까지 구문이 유지, *는*, *b*, *x*, 및 *y* 모든 스레드가에서 읽은 값으로 정의 될 있어야 합니다.  
  
 **예제 2:** 이전 예제와 달리 마스터 스레드에 예를 들어 특정 스레드에서 읽기를 수행 해야 한다고 가정 합니다. 이 경우에 `copyprivate` 브로드캐스트를 직접 할 절을 사용할 수 없지만 공유 임시 개체에 대 한 액세스를 제공 하 여 사용할 수 있습니다.  
  
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
  
 **예제 3:** 병렬 영역 내부에서는 필요한 잠금 개체 수가 입력 하기 전에 쉽게 확인할 수 없으므로 있다고 가정 합니다. `copyprivate` 병렬 해당 지역 내에서 할당 된 공유 잠금 개체에 대 한 액세스를 제공 하 여 절을 사용할 수 있습니다.  
  
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