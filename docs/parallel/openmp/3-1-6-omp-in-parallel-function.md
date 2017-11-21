---
title: "3.1.6 omp_in_parallel 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b72351095fd56ae6543c2ca742983eef315f2158
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="316-ompinparallel-function"></a>3.1.6 omp_in_parallel 함수
**omp_in_parallel** 함수 병렬로 실행 되는 병렬 영역 동적 범위 내에서 호출 되 면 0이 아닌 값을 반환; 그렇지 않으면 0을 반환 합니다. 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
int omp_in_parallel(void);  
```  
  
 이 함수는 serialize 되는 중첩 된 영역을 포함 하 여 병렬로 실행 되는 영역 내에서 호출 하는 경우 0이 아닌 값을 반환 합니다.