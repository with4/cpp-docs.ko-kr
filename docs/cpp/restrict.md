---
title: "제한 | Microsoft Docs"
ms.custom: 
ms.date: 02/09/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- restrict_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], restrict
- restrict __declspec keyword
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ec1a54e9c4f235de4aad796586cd7be3e7ee592e
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/13/2018
---
# <a name="restrict"></a>restrict

**Microsoft 전용**

함수 선언 또는 포인터 형식을 반환 하는 정의에 적용 될 때 `restrict` 함수가 아닌 개체를 반환 하도록 컴파일러에 지시 *별칭*, 즉, 다른 포인터에서 참조 합니다. 따라서 컴파일러 최적화를 수행할 수 있습니다.

## <a name="syntax"></a>구문

> **__declspec(restrict)** *pointer_return_type* *function*();  
  
## <a name="remarks"></a>설명

컴파일러는 전파 `__declspec(restrict)`합니다. 예를 들어 CRT `malloc` 함수에는 `__declspec(restrict)` 장식 및 이므로 컴파일러 가정 하 여 메모리 위치로 초기화 된 포인터 `malloc` 도 별칭을 지정 하 여 없는 이전에 기존 포인터입니다.

컴파일러는 반환 된 포인터가 실제로 별칭이 지정 되지 않음을 확인 하지 않습니다. 프로그램에서 `restrict __declspec` 한정자로 표시된 포인터에 별칭을 지정하지 않도록 확인하는 것은 개발자의 책임입니다.  
  
변수에서와 유사한 의미 체계에 대 한 참조 [__restrict](../cpp/extension-restrict.md)합니다.
 
함수 내에서 앨리어싱에 적용 되는 다른 주석 참조 [__declspec(noalias)](../cpp/noalias.md)합니다.
  
에 대 한 내용은 **제한** c + + AMP의 일부인 키워드 참조 [제한 (c + + AMP)](../cpp/restrict-cpp-amp.md)합니다.  
 
## <a name="example"></a>예  

다음 샘플의 사용법을 보여줍니다 `__declspec(restrict)`합니다.

때 `__declspec(restrict)` 는 포인터를 반환이는 컴파일러가 반환 값에서 가리키는 메모리가 별칭이 지정 되지 않는 함수에 적용 됩니다. 이 예제에서는 포인터 `mempool` 및 `memptr` 은 전체적으로 되므로 컴파일러가 참조 하는 메모리가 별칭이 지정 되지 않는 확신할 수 없습니다. 내에서 사용 되는 반면 `ma` 와 해당 호출자가 `init` 하므로 프로그램에서 참조 하지 않으면 되지 않으면 메모리를 반환 하는 방식으로 `__decslpec(restrict)` 최적화 프로그램이 하는 데 사용 됩니다. 어떻게 CRT 헤더를 장식 하는 할당 함수와 같은 것과 비슷합니다 `malloc` 를 사용 하 여 `__declspec(restrict)` 를 나타내는 항상 기존 포인터에 의해 별칭이 지정 될 수 없는 메모리를 반환 합니다.

```C
// declspec_restrict.c
// Compile with: cl /W4 declspec_restrict.c
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
            a[i*n+j] = 0.1f/k++;
    return a;
}

void multiply(float * a, float * b, float * c)
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

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[키워드](../cpp/keywords-cpp.md)  
[__declspec](../cpp/declspec.md)  
[__declspec(noalias)](../cpp/noalias.md)  
