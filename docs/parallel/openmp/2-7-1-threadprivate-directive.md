---
title: "2.7.1 threadprivate Directive | Microsoft Docs"
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
ms.assetid: 08e0b70f-5359-4607-b0ca-38c2d570d7b3
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.1 threadprivate Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`threadprivate` 지시문을 사용 하면 명명 된 파일 범위, 네임 스페이스 범위, 또는 지정 된 정적 블록 범위 변수는  *변수 목록* 스레드를 개인.  *변수 목록* 형식 없는 변수가 쉼표로 구분 된 목록입니다.  구문에는 `threadprivate` 지시문은 다음과 같습니다:  
  
```  
#pragma omp threadprivate(variable-list) new-line  
```  
  
 각 복사본은 `threadprivate` 변수 초기화는 한 번 프로그램 이전에 첫 번째 참조가 해당 복사본에 대 한 일반적인 방법으로 알 수 없는 지점 \(즉, 마스터 복사본에서 직렬 실행 프로그램의 초기화 되었습니다 대로\).  개체의 명시적 이니셜라이저에 참조 되는 경우는 `threadprivate` 변수 및 개체의 값을 수정할 첫 번째 참조 변수를 복사본을 하기 전에 다음 동작이 지정 되지 않습니다.  
  
 모든 개인 변수를 스레드가 다른 스레드의 복사본을 참조 하지 않아야 하는 것은 `threadprivate` 개체입니다.  직렬 영역 및 프로그램의 마스터 영역 중 마스터 스레드 개체의 복사본으로 참조 됩니다.  
  
 첫 번째 병렬 영역을 실행 하면, 데이터는 `threadprivate` 면 동적 메커니즘 사용 안 함 및 스레드 병렬 모든 지역에 대해 변경 되지 않습니다 경우 되었습니다만 유지 하는 데 반드시 개체.  
  
 제한에는 `threadprivate` 지시어는 다음과 같습니다.  
  
-   A `threadprivate` 지시문 파일 범위 또는 네임 스페이스 범위 변수에 대 한 정의 또는 선언에서 외부 표시 되어야 하며 어휘 목록에 모든 참조 하는 변수 앞에 있어야 합니다.  
  
-   각 변수에  *변수 목록* 의 `threadprivate` 지시문 파일 또는 네임 스페이스 범위에서 변수 선언을 구문적으로 지시문 앞에 파일 또는 네임 스페이스 범위를 참조 해야 합니다.  
  
-   A `threadprivate` 범위 변수 및 중첩 된 범위에 있지 않은 지시문 블록 범위 정적 변수에 대 한 나타나야 합니다.  지시문의 목록에 모든 참조 하는 변수를 구문적으로 보다 빨라야 합니다.  
  
-   각 변수에  *변수 목록* 의 한 `threadprivate` 지시문 블록 범위에서 변수 선언을 구문적으로 지시문 앞에 동일한 범위를 참조 해야 합니다.  변수 선언에서 정적 저장소 클래스 지정자를 사용 해야 합니다.  
  
-   변수에 지정 된 경우는 `threadprivate` 지시문에서 하나의 번역 단위에서 지정 해야는 `threadprivate` 지시문에서 선언 된 각 번역 단위입니다.  
  
-   A `threadprivate` 변수를 제외 하 고는 절에 나타나야 합니다는 `copyin`, `copyprivate`, `schedule`, `num_threads`, 나는  **경우** 절.  
  
-   주소는 `threadprivate` 변수 주소 상수가 아닙니다.  
  
-   A `threadprivate` 형식 또는 참조 형식 변수가 있어야지 않습니다.  
  
-   A `threadprivate` 포드 클래스 형식의 변수에 명시적 이니셜라이저를 선언 하는 경우 액세스할 수 있는, 분명 복사 생성자에 있어야 합니다.  
  
 다음 예제에서는 변수 이니셜라이저에 나타납니다 수정 지정 하지 않은 동작이 발생할 수 있습니다 어떻게 및 보조 개체와 복사 생성자를 사용 하 여이 문제를 방지 하는 방법을 보여 줍니다.  
  
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
  
## 상호 참조:  
  
-   동적 스레드를 참조 하십시오.  [섹션 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 페이지에 있습니다.  
  
-   `OMP_DYNAMIC`환경 변수를 참조 하십시오  [단원 4.3](../../parallel/openmp/4-3-omp-dynamic.md) 49 페이지입니다.