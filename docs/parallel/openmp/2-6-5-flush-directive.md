---
title: "2.6.5 flush 지시문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: a2ec5f74-9c37-424a-8376-47ab4a5829a2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7607070692941606b863be9248b2d69f093f3a13
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="265-flush-directive"></a>2.6.5 flush 지시문
**플러시** 지시문을 명시적 또는 묵시적 여부를 지정 되는 구현이 팀의 모든 스레드가 (아래)에 지정 하는 특정 개체의 일관 된 뷰를 갖도록 하는 데 필요 "스레드 간" 시퀀스 위치 메모리입니다. 이 해당 개체를 참조 하는 식에 대 한 이전 평가 완료 하 고 다음 계산은 수행이 아직 시작 되지 않은 의미 합니다. 예를 들어 컴파일러 메모리, 레지스터에서 개체의 값에 복원 해야 하 고 하드웨어 메모리에 대 한 쓰기 버퍼를 플러시하고 메모리에서 개체의 값을 다시 로드 해야 할 수 있습니다.  
  
 구문은 **플러시** 지시문은 다음과 같습니다.  
  
```  
#pragma omp flush [(variable-list)]  new-line  
```  
  
 동기화를 필요로 하는 개체 모두 지정할 수 있습니다 변수인 경우 선택적에 해당 변수를 지정할 수 있습니다 *변수 목록*합니다. 에 대 한 포인터 있으면는 *변수 목록*, 포인터 자체 플러시, 개체가 아닌 포인터를 참조 합니다.  
  
 A **플러시** 없이 지시문는 *변수 목록* 자동 저장 기간이 있는 액세스할 수 없는 개체를 제외한 모든 공유 개체를 동기화 합니다. (이 경우 보다 더 많은 오버 헤드가 발생할 수 있습니다는 **플러시** 와 *변수 목록*.) A **플러시** 없이 지시문는 *변수 목록* 다음 지시문에 대 한 암시 됩니다.  
  
-   `barrier`  
  
-   항목의 시작과 종료가에서 **중요**  
  
-   항목의 시작과 종료가에서`ordered`  
  
-   항목의 시작과 종료가에서 **병렬**  
  
-   At에서 나오려면 **에 대 한**  
  
-   At에서 나오려면 **섹션**  
  
-   At에서 나오려면 **단일**  
  
-   항목의 시작과 종료가에서 **에 대 한 병렬**  
  
-   항목의 시작과 종료가에서 **병렬 섹션**  
  
 지시문의 경우 지정 하지 않는 한 `nowait` 절이 있는 합니다. 점에 유의 해야 하는 **플러시** 지시문 다음에 대 한 포함 되지 않습니다.  
  
-   항목을 **에 대 한**  
  
-   항목을 또는 종료를 **마스터**  
  
-   입력 **섹션**  
  
-   항목을 **단일**  
  
 Volatile 한정 형식의 개체의 값에 액세스 하는 참조 처럼 동작 개가 **플러시** 이전 시퀀스 지점에서 해당 개체를 지정 하는 지시문입니다. Volatile 한정 형식의 개체의 값을 수정 하는 참조 처럼 동작 개가 **플러시** 다음 시퀀스 지점에서 해당 개체를 지정 하는 지시문입니다.  
  
 되므로 **플러시** 지시문은 C 언어 문 구문의 일환으로, 프로그램에서의 위치에 몇 가지 제한이 있습니다. 참조 [부록 C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) 정식 문법에 대 한 합니다. 다음 예제에서는 이러한 제한 사항을 보여 줍니다.  
  
```  
/* ERROR - The flush directive cannot be the immediate  
*          substatement of an if statement.  
*/  
if (x!=0)  
   #pragma omp flush (x)  
...  
  
/* OK - The flush directive is enclosed in a  
*      compound statement  
*/  
if (x!=0) {  
   #pragma omp flush (x)  
}  
```  
  
 에 대 한 제한 된 **플러시** 지시문은 다음과 같습니다.  
  
-   에 지정 된 변수는 **플러시** 지시문 참조 형식을 사용할 수 없습니다.