---
title: 4.4 OMP_NESTED | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1779b75774a2177a0d6a4f0661406e28b479a7ee
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="44-ompnested"></a>4.4 OMP_NESTED
`OMP_NESTED` 환경 변수 사용 하거나 중첩 된 병렬 처리는 사용 하도록 설정 하거나 호출 하 여 사용 하지 않도록 설정 하지 않으면 중첩 된 병렬 처리를 사용 하지 않도록 설정 된 `o` **mp_set_nested** 라이브러리 루틴입니다. 경우로 설정 **TRUE**, 중첩 된 병렬 처리를 사용 하면로 설정 되어 있으면 **FALSE**중첩 된 병렬 처리를 사용 하지 않도록 설정 합니다. 기본값은 **FALSE**합니다.  
  
 예제:  
  
```  
setenv OMP_NESTED TRUE  
```  
  
## <a name="cross-reference"></a>상호 참조를 삽입 합니다.  
  
-   `omp_set_nested` 함수, 참조 [섹션 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 페이지.