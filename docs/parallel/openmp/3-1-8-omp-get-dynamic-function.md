---
title: 3.1.8 omp_get_dynamic 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af7755173ab884a40a5f8a41f432f265cc1e6c32
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686193"
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