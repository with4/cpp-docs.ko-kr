---
title: "3.1.6 omp_in_parallel 함수 | Microsoft Docs"
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
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e5d05af81eb112894ca27a7599c271138893ee1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="316-ompinparallel-function"></a>3.1.6 omp_in_parallel 함수
**omp_in_parallel** 함수 병렬로 실행 되는 병렬 영역 동적 범위 내에서 호출 되 면 0이 아닌 값을 반환; 그렇지 않으면 0을 반환 합니다. 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
int omp_in_parallel(void);  
```  
  
 이 함수는 serialize 되는 중첩 된 영역을 포함 하 여 병렬로 실행 되는 영역 내에서 호출 하는 경우 0이 아닌 값을 반환 합니다.