---
title: "3. 런타임 라이브러리 함수 | Microsoft Docs"
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
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f1cbedf8782c9c5ccb25bda3f8b43df8a526f268
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="3-run-time-library-functions"></a>3. 런타임 라이브러리 함수
이 섹션에서는 OpenMP C 및 c + + 런타임 라이브러리 함수에 설명 합니다. 헤더  **\<omp.h >** 두 형식, 제어 및 병렬 실행 환경 쿼리 및 데이터에 대 한 액세스를 동기화 하는 데 사용할 수 있는 함수를 잠그는 데 사용할 수 있는 여러 함수를 선언 합니다.  
  
 형식 **omp_lock_t** 는 개체 형식이 잠겨를 사용할 수를 표현할 수 있는 또는 스레드는 잠금을 소유 하 고 있습니다. 이러한 잠금은 라고 *간단한 잠금을*합니다.  
  
 형식 **omp_nest_lock_t** 은 중 하나를 표현할 수 있는 개체 유형의 잠금을 사용할 수 없거나 잠금을 소유 하는 스레드의 id 및 *개수 중첩* (아래 설명 참조). 이러한 잠금은 라고 *중첩 잠금*합니다.  
  
 라이브러리 함수는 "C" 링크 된 외부 함수입니다.  
  
 이 장에서 설명은 다음 항목으로 나뉩니다.  
  
-   실행 환경 함수 (참조 [섹션 3.1](../../parallel/openmp/3-1-execution-environment-functions.md) 페이지 35).  
  
-   기능 잠금 (참조 [섹션 3.2](../../parallel/openmp/3-2-lock-functions.md) 페이지 41).