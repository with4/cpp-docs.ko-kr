---
title: "작업 공유 지시문의 잘못 된 중첩 보여 주는 A.19 예 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 906e900d-9259-44d6-a095-c1ba9135d269
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a3f8a4e1ca62a77c16dafedd0921ca842d7a048
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="a19---examples-showing-incorrect-nesting-of-work-sharing-directives"></a>A.19   작업 공유 지시문의 잘못된 중첩을 보여 주는 예제
이 섹션의 예는 지시문 중첩 규칙을 설명 합니다. 지시문 중첩에 대 한 자세한 내용은 참조 하십시오. [섹션 2.9](../../parallel/openmp/2-9-directive-nesting.md) 33 페이지입니다.  
  
 다음 예제에서는 호환 되지 않는 때문에 내부 및 외부 `for` 지시문이 중첩 되어 있고 동일한 바인딩할 `parallel` 지시문:  
  
```  
void wrong1(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
      int i, j;  
      #pragma omp for  
      for (i=0; i<n; i++) {  
          #pragma omp for  
              for (j=0; j<n; j++)  
                 work(i, j);  
     }  
   }  
}  
```  
  
 위 예의 다음 동적으로 중첩된 버전 비규격 이기도합니다.  
  
```  
void wrong2(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
    int i;  
    #pragma omp for  
      for (i=0; i<n; i++)  
        work1(i, n);  
  }  
}  
  
void work1(int i, int n)  
{  
  int j;  
  #pragma omp for  
    for (j=0; j<n; j++)  
      work2(i, j);  
}  
```  
  
 다음 예제에서는 호환 되지 않는 때문에 `for` 및 `single` 지시문 중첩 되어 있고 동일한 병렬 영역 바인딩할 때:  
  
```  
void wrong3(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
    int i;  
    #pragma omp for  
      for (i=0; i<n; i++) {  
        #pragma omp single  
          work(i);  
      }  
  }  
}  
```  
  
 다음 예제에서는 호환 되지 않는 때문에 `barrier` 내 지시문는 `for` 교착 상태가 발생할 수 있습니다:  
  
```  
void wrong4(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
    int i;  
    #pragma omp for  
      for (i=0; i<n; i++) {  
        work1(i);  
        #pragma omp barrier  
        work2(i);  
      }  
  }  
}  
```  
  
 다음 예제에서는 호환 되지 않는 때문에 `barrier` 교착 상태에서 발생 때문을 한 번에 하나만 스레드 임계 영역을 시작할 수 있습니다.  
  
```  
void wrong5()  
{  
  #pragma omp parallel  
  {  
    #pragma omp critical  
    {  
       work1();  
       #pragma omp barrier  
       work2();  
    }  
  }  
}  
```  
  
 다음 예제에서는 호환 되지 않는 때문에 `barrier` 때문을 하나의 스레드가 실행 교착 상태에 결과 `single` 섹션:  
  
```  
void wrong6()  
{  
  #pragma omp parallel  
  {  
    setup();  
    #pragma omp single  
    {  
      work1();  
      #pragma omp barrier  
      work2();  
    }  
    finish();  
  }  
}  
```