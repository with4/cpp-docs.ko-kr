---
title: "3.2.5 omp_test_lock and omp_test_nest_lock 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 36818945-c22c-4c24-b754-4e73eba6f3f8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8fcdacdbb38a9bb27e35ada74aa2139be10c6797
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="325-omptestlock-and-omptestnestlock-functions"></a>3.2.5 omp_test_lock and omp_test_nest_lock 함수
이러한 함수는 잠금을 설정 하지 않지만 스레드 실행을 차단 하지 않습니다. 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
int omp_test_lock(omp_lock_t *lock);  
int omp_test_nest_lock(omp_nest_lock_t *lock);  
```  
  
 인수는 초기화 된 잠금 변수를 가리켜야 합니다. 이러한 함수를 동일한 방식으로 잠금을 설정 하려고 합니다. `omp_set_lock` 및 `omp_set_nest_lock`제외 하 고 스레드의 실행을 차단 하지 않습니다.  
  
 간단한 잠금에 대 한는 `omp_test_lock` 잠금을 성공적으로 설정 된 경우 함수는 0이 아닌 값을 반환; 그렇지 않으면 0을 반환 합니다.  
  
 중첩 잠금에 대 한는 `omp_test_nest_lock` 함수 잠금을 성공적으로 설정 된 경우 새 중첩 수를 반환 하 고 않으면 그렇지 않으면 0을 반환 합니다.