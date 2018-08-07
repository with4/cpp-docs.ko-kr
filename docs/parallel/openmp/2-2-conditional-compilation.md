---
title: 2.2 조건부 컴파일 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8f9c914d-736c-48cf-899d-c8029dbe1e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3d8c7073548c015d9982b721387176a0ca658c2
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33685907"
---
# <a name="22-conditional-compilation"></a>2.2 조건부 컴파일
_**OPENMP** 10 진수 상수 OpenMP 규격 구현으로 정의 된 매크로 이름 *yyyymm*, 연도 및 월의 승인 된 사양 됩니다. 이 매크로의 제목을 않아야는 **#define** 또는 **#undef** 전처리 지시문입니다.  
  
```  
#ifdef _OPENMP  
iam = omp_get_thread_num() + index;  
#endif  
```  
  
 확장 OpenMP을 정의 하는 공급 업체, 추가 미리 정의 된 매크로 지정할 수 있습니다.