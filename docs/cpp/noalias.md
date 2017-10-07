---
title: noalias | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- noalias_cpp
dev_langs:
- C++
helpviewer_keywords:
- noalias __declspec keyword
- __declspec keyword [C++], noalias
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: cb8d3425b08984f31954df3a7cf7771e85301a5b
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="noalias"></a>noalias

**Microsoft 전용**

`noalias`함수 호출을 수정 하거나 표시의 글로벌 상태를 참조 하지 않는 의미를 메모리에만 수정 하 고 *직접* 여 포인터 매개 변수 (첫 번째 수준의 간접 참조).

함수에 `noalias`로 주석이 지정된 경우 최적화 프로그램은 매개 변수 자체와 포인터 매개 변수의 1차 간접 참조만 함수 내에서 참조되거나 수정된다고 가정할 수 있습니다. 표시되는 전역 상태는 컴파일 범위 외부에서 정의되거나 참조되지 않는 모든 데이터의 집합이며 해당 주소는 사용되지 않습니다. 컴파일 범위는 모든 소스 파일 ([/LTCG (링크 타임 코드 생성)](../build/reference/ltcg-link-time-code-generation.md) 작성) 또는 단일 소스 파일 (비-**/LTCG** 빌드).

## <a name="example"></a>예제

다음 샘플 코드에서는 `__declspec(restrict)` 및 `__declspec(noalias)`의 사용을 보여 줍니다. 일반적으로에서 반환 된 메모리 `malloc` 은 `restrict` CRT 헤더가 적절 하 게 데코레이팅되기 때문에 있습니다.

그러나이 예에서 포인터 `mempool` 및 `memptr` 은 전역 이므로 컴파일러에서 메모리가 별칭이 적용 되지 않는다고 확신할 수 없습니다. `__declspec(restrict)`를 사용하여 포인터를 반환하는 함수를 데코레이팅하면 반환 값이 가리키는 메모리에 별칭이 지정되지 않음을 컴파일러에 알릴 수 있습니다.

이 예제에서 메모리에 액세스하는 함수를 `__declspec(noalias)`를 사용하여 데코레이팅하면 이 함수가 매개 변수 목록의 포인터를 사용하는 경우를 제외하고 전역 상태에 영향을 주지 않음을 컴파일러에 알릴 수 있습니다.

```C
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

## <a name="see-also"></a>참고 항목

[__declspec](../cpp/declspec.md)  
[키워드](../cpp/keywords-cpp.md)
