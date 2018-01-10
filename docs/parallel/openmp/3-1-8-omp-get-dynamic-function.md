---
title: "3.1.8 omp_get_dynamic 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bd4ec73b82848efcdface781738639b05a256958
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="318-ompgetdynamic-function"></a>3.1.8 omp_get_dynamic 함수
**omp_get_dynamic** 스레드 동적인 조절을 사용 되 고 그렇지 않으면 0을 반환 하는 경우 함수는 0이 아닌 값을 반환 합니다. 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
int omp_get_dynamic(void);  
```  
  
 구현에는 스레드 수의 동적 조정을 구현 하지 않으면,이 함수는 항상 0을 반환 합니다.  
  
## <a name="cross-references"></a>교차 참조:  
  
-   동적 스레드 조정에 대 한 참조 [섹션 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 페이지.