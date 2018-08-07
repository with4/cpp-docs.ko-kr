---
title: 3.2 함수 잠금 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0ec855c6-55a9-49d7-bee4-5edae6e86a1b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cd788b0ef1c72b1f38a44ee608ce0c7760e24adc
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33696255"
---
# <a name="32-lock-functions"></a>3.2 Lock 함수
이 섹션에서 설명 하는 함수에는 동기화에 사용 되는 잠금을 조작 합니다.  
  
 다음 함수에 대 한 잠금 변수 형식이 있어야 합니다 **omp_lock_t**합니다. 이 변수는 이러한 기능을 통해만 액세스 해야 합니다. 모든 잠금 함수에 대 한 포인터를 포함 된 인수 필요 **omp_lock_t** 유형입니다.  
  
-   `omp_init_lock` 함수 단순 잠금을 초기화 합니다.  
  
-   `omp_destroy_lock` 함수에는 간단한 잠금을 제거 합니다.  
  
-   `omp_set_lock` 함수 단순 잠금을 사용할 수 있는 될 때까지 기다립니다.  
  
-   `omp_unset_lock` 함수에는 간단한 잠금을 해제 합니다.  
  
-   `omp_test_lock` 함수 단순 잠금을 테스트 합니다.  
  
 다음 함수에 대 한 잠금 변수 형식이 있어야 합니다 **omp_nest_lock_t**합니다.  이 변수는 이러한 기능을 통해만 액세스 해야 합니다. 모든 중첩 잠금 함수에 대 한 포인터를 포함 된 인수 필요 **omp_nest_lock_t** 유형입니다.  
  
-   `omp_init_nest_lock` 함수 중첩 잠금을 초기화 합니다.  
  
-   `omp_destroy_nest_lock` 함수 중첩 잠금을 제거 합니다.  
  
-   `omp_set_nest_lock` 함수 중첩 잠금을 사용할 수 있는 될 때까지 기다립니다.  
  
-   `omp_unset_nest_lock` 함수 중첩 잠금을 해제 합니다.  
  
-   `omp_test_nest_lock` 함수 중첩 잠금을 테스트 합니다.  
  
 OpenMP 잠금 함수에는 잠금 변수는은 항상 읽고 잠금 변수의 최신 값을 업데이트 하는 방식으로 액세스 합니다. 따라서 명시적 포함 하도록 OpenMP 프로그램 필요 하지 않습니다 **플러시** 지시문을 잠금 변수의 값이 서로 다른 스레드 간에 일치 하는지 확인 합니다. (에 대 한 요구가 있을 수 있습니다 **플러시** 지시문을 다른 변수 값을 일관 되 게 합니다.)