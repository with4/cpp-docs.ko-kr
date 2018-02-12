---
title: noalias | Microsoft Docs
ms.custom: 
ms.date: 02/09/2018
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6fd57b10aba4298ff7facd725ab3ce1934ccf1ab
ms.sourcegitcommit: f3c398b1c7dbf36ab71b5ca89d365b1913afa307
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2018
---
# <a name="noalias"></a>noalias

**Microsoft 전용**

`noalias`함수 호출을 수정 하거나 표시의 글로벌 상태를 참조 하지 않는 의미를 메모리에만 수정 하 고 *직접* 여 포인터 매개 변수 (첫 번째 수준의 간접 참조).

함수에 `noalias`로 주석이 지정된 경우 최적화 프로그램은 매개 변수 자체와 포인터 매개 변수의 1차 간접 참조만 함수 내에서 참조되거나 수정된다고 가정할 수 있습니다. 표시되는 전역 상태는 컴파일 범위 외부에서 정의되거나 참조되지 않는 모든 데이터의 집합이며 해당 주소는 사용되지 않습니다. 컴파일 범위는 모든 소스 파일 ([/LTCG (링크 타임 코드 생성)](../build/reference/ltcg-link-time-code-generation.md) 작성) 또는 단일 소스 파일 (비-**/LTCG** 빌드).

`noalias` 주석은 주석이 추가 된 함수 본문에만 적용 됩니다. 로 함수를 표시 하면 `__declspec(noalias)` 함수로 반환 된 포인터의 별칭을 지정 하는 데 영향을 주지 않습니다.

참조 별칭 지정에 영향을 줄 수 있는 다른 주석 [__declspec (restrict)](../cpp/restrict.md)합니다.

## <a name="example"></a>예

다음 샘플의 사용법을 보여줍니다 `__declspec(noalias)`합니다.

때 함수 `multiply` 에 메모리 액세스 된 주석 처리 `__declspec(noalias)`,이 컴파일러가이 함수는 매개 변수 목록의 포인터를 통해 제외 하 고 전역 상태를 수정 하지 않습니다.

```C
// declspec_noalias.c
#include <stdio.h>
#include <stdlib.h>

#define M 800
#define N 600
#define P 700

float * mempool, * memptr;

float * ma(int size)
{
    float * retval;
    retval = memptr;
    memptr += size;
    return retval;
}

float * init(int m, int n)
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
[__declspec(restrict)](../cpp/restrict.md)  
