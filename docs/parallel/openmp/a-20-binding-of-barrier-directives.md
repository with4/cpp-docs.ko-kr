---
title: "A.20   Binding of barrier Directives | Microsoft Docs"
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
ms.assetid: a3fdcc26-6873-429b-998e-de451401483b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.20   Binding of barrier Directives
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지시문에 대 한 바인딩 규칙에 대 한 호출에  **장벽** 가장 가까운 바깥쪽에 바인딩하려면 지시문 `parallel` 지시문입니다.  지시문 바인딩에 대 한 자세한 내용은 참조 하십시오.  [섹션 2.8](../../parallel/openmp/2-8-directive-binding.md) 32 페이지에 있습니다.  
  
 다음 예제 호출에서  *주* 에  *찾아* 준수 하는 때문에  **장벽** \(에  *sub3*\) 병렬 영역에 바인딩된  *찾아*.  호출에서  *주* 에  *sub1* 준수 하는 때문에  **장벽** 서브루틴의 병렬 영역에 바인딩된  *찾아*.  호출에서  *주* 에  *sub3* 준수 하는 때문에 있는  **장벽** 모든 병렬 영역에 바인딩되지 않습니다, 무시 됩니다.  또한 해당  **장벽** 팀에서 만든 모든 스레드 및 스레드 병렬 영역 바깥쪽에 동기화  *sub1*.  
  
```  
int main()  
{  
    sub1(2);  
    sub2(2);  
    sub3(2);  
}  
  
void sub1(int n)  
{  
    int i;  
    #pragma omp parallel private(i) shared(n)  
    {  
        #pragma omp for  
        for (i=0; i<n; i++)  
            sub2(i);  
    }  
}  
  
void sub2(int k)  
{  
     #pragma omp parallel shared(k)  
     sub3(k);  
}  
  
void sub3(int n)  
{  
    work(n);  
    #pragma omp barrier  
    work(n);  
}  
```