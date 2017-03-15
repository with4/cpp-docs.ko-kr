---
title: "A.24   Example of the private Clause | Microsoft Docs"
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
ms.assetid: f90a5b49-81ff-4746-ae03-37bbd33f6c08
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.24   Example of the private Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`private` 절 \([2.7.2.1 섹션](../../parallel/openmp/2-7-2-1-private.md) 25 페이지\)의 병렬 영역 효과 영역 어휘 범위에 대 한, 동적 범위를 지역에만 있습니다.  뒤에서의 변수 사용 예제를  *는* 내는 `for` 루프 루틴에서  *f* 의 개인 복사본을 참조  *는*, 루틴에서을 사용 하는 동안  *g* 전역 하 참조  *는*.  
  
```  
int a;  
  
void f(int n)   
{  
    a = 0;  
  
    #pragma omp parallel for private(a)  
    for (int i=1; i<n; i++)   
    {  
        a = i;  
        g(i, n);  
        d(a);     // Private copy of "a"  
        ...  
    }  
    ...  
  
void g(int k, int n)   
{  
    h(k,a); // The global "a", not the private "a" in f  
}  
```