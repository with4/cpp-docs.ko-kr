---
title: "noalias | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "noalias"
  - "noalias_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec 키워드[C++], noalias"
  - "noalias __declspec 키워드"
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# noalias
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `noalias`는 함수 호출이 표시되는 전역 상태를 수정하거나 참조하지 않으며 포인터 매개 변수가 `직접` 가리키는\(1차 간접 참조\) 메모리만 수정함을 의미합니다.  
  
 함수에 `noalias`로 주석이 지정된 경우 최적화 프로그램은 매개 변수 자체와 포인터 매개 변수의 1차 간접 참조만 함수 내에서 참조되거나 수정된다고 가정할 수 있습니다.  표시되는 전역 상태는 컴파일 범위 외부에서 정의되거나 참조되지 않는 모든 데이터의 집합이며 해당 주소는 사용되지 않습니다.  컴파일 범위는 모든 소스 파일\([\/LTCG\(링크 타임 코드 생성\)](../build/reference/ltcg-link-time-code-generation.md) 빌드\) 또는 단일 소스 파일\(**\/LTCG** 이외의 빌드\)입니다.  
  
## 예제  
 다음 샘플 코드에서는 `__declspec(restrict)` 및 `__declspec(noalias)`의 사용을 보여 줍니다.  일반적으로 `malloc`에서 반환된 메모리는 CRT 헤더가 적절하게 데코레이팅되기 때문에 `restrict` 및 `noalias`입니다.  
  
 그러나 이 예제에서는 `mempool` 및 `memptr` 포인터가 전역이므로 컴파일러에서 메모리에 별칭이 적용되지 않는다고 확신할 수 없습니다.  `__declspec(restrict)`를 사용하여 포인터를 반환하는 함수를 데코레이팅하면 반환 값이 가리키는 메모리에 별칭이 지정되지 않음을 컴파일러에 알릴 수 있습니다.  
  
 이 예제에서 메모리에 액세스하는 함수를 `__declspec(noalias)`를 사용하여 데코레이팅하면 이 함수가 매개 변수 목록의 포인터를 사용하는 경우를 제외하고 전역 상태에 영향을 주지 않음을 컴파일러에 알릴 수 있습니다.  
  
```  
// declspec_noalias.c   
#include <stdio.h>  
#include <stdlib.h>  
  
#define M 800  
#define N 600  
#define P 700  
  
float * mempool, * memptr;  
  
__declspec(restrict) float * ma(int size)  
{  
    float * retval;  
    retval = memptr;  
    memptr += size;  
    return retval;  
}  
  
__declspec(restrict) float * init(int m, int n)  
{  
    float * a;  
    int i, j;  
    int k=1;  
  
    a = ma(m * n);  
    if (!a) exit(1);  
    for (i=0; i<m; i++)  
        for (j=0; j<n; j++)  
            a[i*n+j] = 0.1/k++;  
    return a;  
}  
  
__declspec(noalias) void multiply(float * a, float * b, float * c)  
{  
    int i, j, k;  
  
    for (j=0; j<P; j++)  
        for (i=0; i<M; i++)  
            for (k=0; k<N; k++)  
                c[i * P + j] =   
                          a[i * N + k] *   
                          b[k * P + j];  
}  
  
int main()  
{  
    float * a, * b, * c;  
  
    mempool = (float *) malloc(sizeof(float) * (M*N + N*P + M*P));  
  
    if (!mempool)   
    {  
        puts("ERROR: Malloc returned null");  
        exit(1);  
    }  
  
    memptr = mempool;  
    a = init(M, N);  
    b = init(N, P);  
    c = init(M, P);  
  
    multiply(a, b, c);  
}  
```  
  
## 참고 항목  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)