---
title: "2.6.4 atomic 구문 | Microsoft Docs"
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
ms.assetid: e4232ef1-4058-42ce-9de0-0ca788312aba
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.4 atomic 구문
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

 `atomic` 지시어를 사용 하면 다 수의 가능성에 노출 하는 대신 특정 메모리 위치를 개별적으로 업데이트 되도록 동시 스레드를 작성 합니다. 구문은 `atomic` 지시문은 다음과 같습니다.  
  
```  
#pragma omp atomic new-lineexpression-stmt  
```  
  
 식 문의 다음 형식 중 하나가 있어야 합니다.  
  
 *x binop*= *expr*  
  
 x + +  
  
 + + x  
  
 x-  
  
 --x  
  
 위 식:  
  
-   *x* 스칼라 형식의 lvalue 식입니다.  
  
-   *expr* 스칼라 형식이 포함 된 식을 이며가 지정 된 개체를 참조 하지 않는 *x*합니다.  
  
-   `binop` 오버 로드 된 연산자 아니며 중 하나는 +, *,-, /, &, ^, &#124; <\<, 또는 >> 합니다.  
  
 없지만 구현 정의 여부 구현에서는 모든 대체 `atomic` 지시문으로 **중요 한** 동일한 고유 지시문 *이름*,  `atomic` 지시문 허용 향상 된 최적화 합니다. 하드웨어 지침 자주 사용할 수 있는 오버 헤드가 가장 인 원자성 업데이트를 수행할 수 있는 합니다.  
  
 부하 및가 지정 된 개체의 저장소 *x* 은;의 평가 *expr* 는 원자성이 아닙니다. 경합 상태를 방지 하려면으로 병렬로 위치의 모든 업데이트를 보호는 `atomic` 지시문을 제외한 경합 조건이 없는 것으로 알려져 있습니다.  
  
 에 대 한 제한 된 `atomic` 지시문은 다음과 같습니다.  
  
-   호환 가능한 형식을 가질 수 프로그램 전체에서 x 저장소 위치에 대 한 모든 원자 참조가 필요 합니다.  
  
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