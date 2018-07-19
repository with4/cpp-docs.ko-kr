---
title: 2.7.1 threadprivate 지시문 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 08e0b70f-5359-4607-b0ca-38c2d570d7b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c9912ccbfa6f5773ec1e523245f75e675bb82244
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692654"
---
# <a name="271-threadprivate-directive"></a>2.7.1 threadprivate 지시문
`threadprivate` 명명 된 파일 범위, 네임 스페이스 범위 또는 블록 범위의 정적 변수에 지정 된 지시문을 사용 하면는 *변수 목록* 스레드에 한정 합니다. *변수 목록* 불완전 한 형식을 갖지 않는 변수의 쉼표로 구분 된 목록입니다. 구문은 `threadprivate` 지시문은 다음과 같습니다.  
  
```  
#pragma omp threadprivate(variable-list) new-line  
```  
  
 각 복사본은 `threadprivate` 변수가 초기화 됩니다 한 번 해당 복사본에 대 한 첫 번째 참조 이전 버전의 프로그램에는 일반적인 방법으로 지정 되지 않은 시점 (즉, 프로그램의 직렬 실행에 마스터 복사본을 초기화할 수는). 경우에 개체의 명시적 initializer에서 참조 되는 `threadprivate` 변수와 개체의 값은 변수 복사본에 대 한 첫 번째 참조 하기 전에 수정 되 다음 동작이 지정 되지 않습니다.  
  
 모든 개인 변수와 스레드의 다른 스레드 복사본 참조 하지 않아야 하는 대로 `threadprivate` 개체입니다. 직렬 영역 및 프로그램의 마스터 지역 중 참조 된 개체의 마스터 스레드에 복사본을 됩니다.  
  
 첫 번째 병렬 영역을 실행 한 후의 데이터는 `threadprivate` 개체 동적 메커니즘 스레드 경우 비활성화 된 모든 병렬 영역에 대 한 변경 되지 않은 상태로 유지 되는 스레드 수 및 지 속성이 보장 됩니다.  
  
 시의 제한 된 `threadprivate` 지시문은 다음과 같습니다.  
  
-   A `threadprivate` 파일 범위 또는 네임 스페이스 범위 변수에 대 한 지시문 정의 또는 선언 외부에 나타나야 하 고 앞에 변수 중 하나에 대 한 모든 참조의 목록에 어휘 적으로 야 합니다.  
  
-   각 변수에 *변수 목록* 의 `threadprivate` 어휘 적으로 지시문 앞에 있는 파일이 나 네임 스페이스 범위에서 변수 선언이 지시문 파일이 나 네임 스페이스 범위에서 참조 해야 합니다.  
  
-   A `threadprivate` 중첩 된 범위 아니라 변수의 범위에 정적 블록 범위 변수에 대 한 지시문이 나타나야 합니다. 지시문의 목록에 변수 중 하나에 대 한 모든 참조 앞에 어휘 적으로 해야 합니다.  
  
-   각 변수에 *변수 목록* 의 `threadprivate` 어휘 적으로 지시문 앞에 있는 동일한 범위에서 변수 선언 지시문 블록 범위에서 참조 해야 합니다. 변수 선언에 정적 저장소 클래스 지정자를 사용 해야 합니다.  
  
-   변수에서 지정 되 면 한 `threadprivate` 번역 단위에 지시문을 지정 해야에 `threadprivate` 선언 된 각 변환 단위에서 지시문입니다.  
  
-   A `threadprivate` 변수를 제외 하 고 모든 절에 나타나지 않아야는 `copyin`, `copyprivate`, `schedule`, `num_threads`, 또는 **경우** 절.  
  
-   주소는 `threadprivate` 변수 주소 상수가 아닙니다.  
  
-   A `threadprivate` 불완전 한 형식 또는 참조 형식 변수에 있어야 합니다.  
  
-   A `threadprivate` 명시적 이니셜라이저와 함께 선언 되는 경우 비 POD 클래스 형식의 변수에 액세스 가능 하며 명확한 복사 생성자가 있어야 합니다.  
  
 다음 예제에서는 또한 방법을 이니셜라이저에 표시 되는 변수를 수정 하면 지정 되지 않은 동작이 보조 개체 및 복사 생성자를 사용 하 여이 문제를 방지 하는 방법을 보여 줍니다.  
  
```  
int x = 1;  
T a(x);  
const T b_aux(x); /* Capture value of x = 1 */  
T b(b_aux);  
#pragma omp threadprivate(a, b)  
  
void f(int n) {  
   x++;  
   #pragma omp parallel for  
   /* In each thread:  
   * Object a is constructed from x (with value 1 or 2?)  
   * Object b is copy-constructed from b_aux  
   */  
   for (int i=0; i<n; i++) {  
      g(a, b); /* Value of a is unspecified. */  
   }  
}  
```  
  
## <a name="cross-references"></a>교차 참조:  
  
-   동적 스레드 참조 [섹션 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 페이지.  
  
-   `OMP_DYNAMIC` 환경 변수를 참조 [섹션 4.3](../../parallel/openmp/4-3-omp-dynamic.md) 페이지 49에 있습니다.