---
title: "알고리즘 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- libraries [C++], C++ algorithm conventions
- algorithms [C++], C++
- C++ Standard Library, algorithms
- algorithm template function C++ library conventions
- conventions [C++], C++ algorithm
ms.assetid: dec9b373-7d5c-46cc-b7d2-21a938ecd0a6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5bc9d57f93b5d3ee537330ab16c2c9a02b6beead
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2018
---
# <a name="algorithms"></a>알고리즘
알고리즘은 C++ 표준 라이브러리의 기본적인 부분입니다. 알고리즘은 컨테이너 자체가 아니라 반복기에서 작동합니다. 따라서 모두는 아니지만 대부분의 C++ 표준 라이브러리 컨테이너에서 동일한 알고리즘을 사용할 수 있습니다. 이 섹션에서는 C++ 표준 라이브러리 알고리즘의 규칙 및 용어를 설명합니다.  
  
## <a name="remarks"></a>설명  
 알고리즘 템플릿 함수에 대한 설명은 다음과 같은 여러 약어 구를 사용합니다.  
  
-   "[*A*, *B*) 범위" 구는 *A*부터 *B*까지(포함 안 함) 0개 이상 불연속 값의 시퀀스를 의미합니다. 범위는 *A;*에서 *B*에 연결할 수 있는 경우에만 유효합니다. *N* (*N* = *A*) 개체에 *A*를 저장하고, 개체를 0번 이상(++*N*) 증가시키고, 유한 증분 수(N == B*)* 후에 개체가 *B*와 같도록 할 수 있습니다.  
  
-   "[*A*, *B*) 범위의 각 *N*" 구는 *N*이 *A* 값으로 시작하고 *B* 값과 같을 때까지 0번 이상 증분됨을 의미합니다. *N* == *B*의 경우는 범위에 포함되지 않습니다.  
  
-   "*X*인 [*A*, *B*) 범위의 가장 낮은 값 *N*"은 *X* 조건이 충족될 때까지 *X* 조건이 [*A*, *B*) 범위의 각 *N*에 대해 확인됨을 의미합니다.  
  
-   "*X*인 [*A*, *B*) 범위의 가장 높은 값 *N*"은 *X*가 [*A*, *B*) 범위의 각 *N*에 대해 확인됨을 의미합니다. 함수는 *X* 조건이 충족될 때마다 *N*의 복사본을 `K`에 저장합니다. 이러한 저장이 발생하는 경우 함수는 *B*와 같은 *N*의 최종 값을 `K`로 바꿉니다. 그러나 양방향 또는 임의 액세스 반복기의 경우 *N*이 범위의 가장 높은 값부터 시작하고 *X* 조건이 충족될 때까지 범위에서 감소함을 의미할 수도 있습니다.  
  
-   *X* - *Y*와 같은 식입니다. 여기서 *X* 및 *Y*는 임의 액세스 반복기 이외의 반복기일 수 있으며 수학적 의미로 사용됩니다. 이러한 값을 확인해야 하는 경우 함수가 반드시 **-** 연산자를 평가하는 것은 아닙니다. *X* + *N* 및 *X* - *N* 같은 식에 대해서도 마찬가지입니다. 여기서 *N*은 정수 형식입니다.  
  
 여러 알고리즘이 `operator==`의 경우처럼 Pairwise 비교를 수행하는 조건자를 사용하여 `bool` 결과를 생성합니다. 조건자 함수 `operator==` 또는 해당 대체 항목은 피연산자 중 하나를 변경하면 안 됩니다. 평가할 때마다 동일한 `bool` 결과를 생성해야 하며, 두 피연산자 중 하나의 복사본을 피연산자에 대체할 경우 동일한 결과를 생성해야 합니다.  
  
 여러 알고리즘이 시퀀스의 요소 쌍에 대해 엄격하고 약한 순서를 적용해야 하는 조건자를 사용합니다. `pr`(*X*, *Y*) 조건자의 경우:  
  
-   엄격은 `pr`(*X*, *X*)가 false임을 의미합니다.  
  
-   !`pr`(*X*, *Y*) && !`pr`(*Y*, *X*)인 경우 약함은 *X* 및 *Y*에 동일한 순서가 지정됨을 의미합니다(*X* == *Y*를 정의할 필요가 없음).  
  
-   순서 지정은 `pr`(*X*, *Y*) && `pr`(*Y*, Z)가 `pr`(*X*, Z)를 암시함을 의미합니다.  
  
 이러한 알고리즘 중 일부는 *X* \< *Y* 조건자를 암시적으로 사용합니다. 일반적으로 엄격하고 약한 순서 요구 사항을 충족하는 다른 조건자는 *X* > *Y*, **less**(*X*, *Y*) 및 `greater`(*X*, *Y*)입니다. 그러나 *X* \<= *Y* 및 *X* >= *Y*와 같은 조건자는 이 요구 사항을 충족하지 않습니다.  
  
 [`First`, `Last`) 범위에서 반복기에 의해 지정된 요소의 시퀀스는 [0, `Last` - `First`) 범위의 각 *N* 및 (N, `Last` - `First`) 범위의 각 *M*에 대해 !(\*(`First` + *M*) < \*(*First* + *N*))이 참인 경우 **<** 연산자에 의해 순서가 지정되는 시퀀스입니다. 요소는 오름차순으로 정렬됩니다. 조건자 함수 **operator<** 또는 해당 대체 항목은 피연산자 중 하나를 변경하면 안 됩니다. 평가할 때마다 동일한 `bool` 결과를 생성해야 하며, 두 피연산자 중 하나의 복사본을 피연산자에 대체할 경우 동일한 결과를 생성해야 합니다. 또한 비교하는 피연산자에 엄격하고 약한 순서를 적용해야 합니다.  
  
 [`First`, `Last`) 범위에서 반복기에 의해 지정된 요소의 시퀀스는 [1, `Last` - `First`) 범위의 각 *N*에 대해 조건자 !(\*`First` < \*(`First` + *N*))이 참인 경우 **operator<**에 의해 순서가 지정되는 힙입니다. 첫 번째 요소가 가장 큽니다. 내부 구조는 템플릿 함수에만 알려진 [make_heap](../standard-library/algorithm-functions.md#make_heap), [pop_heap](../standard-library/algorithm-functions.md#pop_heap), 및 [push_heap](../standard-library/algorithm-functions.md#push_heap)합니다. 순서가 지정된 시퀀스와 마찬가지로, 조건자 함수 **operator<** 또는 해당 대체 항목은 피연산자 중 하나를 변경하면 안 되며, 비교하는 피연산자에 엄격하고 약한 순서를 적용해야 합니다. 평가할 때마다 동일한 `bool` 결과를 생성해야 하며, 두 피연산자 중 하나의 복사본을 피연산자에 대체할 경우 동일한 결과를 생성해야 합니다.  
  
 C++ 표준 라이브러리 알고리즘은 [\<algorithm>](../standard-library/algorithm.md) 및 [\<numeric>](../standard-library/numeric.md) 헤더 파일에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)   
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)

