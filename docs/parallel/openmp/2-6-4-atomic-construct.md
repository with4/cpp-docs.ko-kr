---
title: 2.6.4 atomic 구문 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e4232ef1-4058-42ce-9de0-0ca788312aba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3c906a9a9b781f742f525688b77d5f58da16bb10
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39208135"
---
# <a name="264-atomic-construct"></a>2.6.4 atomic 구문
`atomic` 지시문 하면 다 수의 가능성에 노출 하는 대신 특정 메모리 위치를 개별적으로 업데이트 되는 동시 스레드를 작성 합니다. 구문의 `atomic` 지시문은 다음과 같습니다.  
  
```  
#pragma omp atomic new-lineexpression-stmt  
```  
  
 식 문에 다음 형식 중 하나가 있어야 합니다.  
  
 *x binop*= *expr*  
  
 x + +  
  
 + + x  
  
 x-  
  
 --x  
  
 이전 식:  
  
-   *x* 스칼라 형식의 lvalue 식입니다.  
  
-   *expr* 스칼라 형식이 있는 식을 이며 지정 된 개체를 참조 하지 않습니다 *x*합니다.  
  
-   `binop` 오버 로드 된 연산자 아니며 중 하나인 +, \*,-, /, &, ^, &#124;, <\<, 또는 >> 합니다.  
  
 이지만 구현 시 정의 된 구현을 모두 대체 여부 `atomic` 사용 하 여 지시문 **중요 한** 동일한 고유 지시문 *이름*는 `atomic` 지시문 콘텐츠 최적화를 향상 합니다. 하드웨어 관련 지침은 종종 오버 헤드가 가장을 사용 하 여 원자성 업데이트를 수행할 수 있는 합니다.  
  
 부하 및 지정 된 개체의 저장소 *x* 은; 평가 *expr* 원자성이 아닙니다. 경합 상황을 방지 하려면 사용 하 여 병렬로 위치의 모든 업데이트를 보호 합니다 `atomic` 경합의 사용 가능한 것으로 알려진 제외한 지시문입니다.  
  
 에 대 한 제한 된 `atomic` 지시문은 다음과 같습니다.  
  
-   프로그램 전체에서 저장소 위치 x에 대 한 모든 원자성 참조 형식이 호환 해야 합니다.  
  
## <a name="examples"></a>예를 들면 다음과 같습니다.  
  
```  
extern float a[], *p = a, b;  
/* Protect against races among multiple updates. */  
#pragma omp atomic  
a[index[i]] += b;  
/* Protect against races with updates through a. */  
#pragma omp atomic  
p[i] -= 1.0f;  
  
extern union {int n; float x;} u;  
/* ERROR - References through incompatible types. */  
#pragma omp atomic  
u.n++;  
#pragma omp atomic  
u.x -= 1.0f;  
```