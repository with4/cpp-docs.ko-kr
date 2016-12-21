---
title: "A.19   Examples Showing Incorrect Nesting of Work-sharing Directives | Microsoft Docs"
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
ms.assetid: 906e900d-9259-44d6-a095-c1ba9135d269
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.19   Examples Showing Incorrect Nesting of Work-sharing Directives
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

중첩 지시문 규칙을 설명 하는이 절에 있는 예제입니다.  중첩 지시문에 대 한 자세한 내용은  [2.9 절](../../parallel/openmp/2-9-directive-nesting.md) 33 페이지에 있습니다.  
  
 다음 예제에서는 정책을 준수 하지 않는 것 때문에 내부 및 외부 `for` 지시문에 중첩 된 및 동일한 바인딩 `parallel` 지시문:  
  
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
  
 또한 다음 동적으로 중첩 된 버전은 위의 예제 정책 위반입니다.  
  
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
  
 다음 예제에서는 정책을 준수 하지 않는 것 때문에 `for` 및 `single` 지시문을 중첩 하 고 같은 병렬 영역에 바인딩할.  
  
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
  
 다음은 정책을 준수 하지 않는 것 때문에 `barrier` 지시문 내에 `for` 교착 상태가 발생할 수 있습니다.  
  
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
  
 다음은 정책을 준수 하지 않는 것 때문에 `barrier` 한 번에 하나의 스레드가 임계 섹션에 들어갈 수 있습니다 때문에 교착 상태가 발생 합니다.  
  
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
  
 다음 예제에서는 정책을 준수 하지 않는 것 때문에 `barrier` 하나의 스레드로 실행 때문에 교착 상태가 발생의 `single` 섹션:  
  
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