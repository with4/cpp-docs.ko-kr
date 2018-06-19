---
title: 기본 (OpenMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- default
dev_langs:
- C++
helpviewer_keywords:
- default OpenMP clause
- defaults, OpenMP clause
ms.assetid: 96055106-a8f0-40b3-8319-e412b6e07bf8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9fc39951270138e9bd243172b289e7bd96190f14
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692323"
---
# <a name="default-openmp"></a>default (OpenMP)
병렬 영역에서 범위가 지정 되지 않은 변수 동작을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
default(shared | none)  
```  
  
## <a name="remarks"></a>설명  
 `shared`적용 되는 경우는 `default` 절을 지정 하지 않으면으로 지정 된 경우에 따라 병렬 영역에 있는 변수를 처리할 수 있음을 의미는 [공유](../../../parallel/openmp/reference/shared-openmp.md) 절. `none` 즉 병렬 지역으로 범위가 한정 되지 않습니다에 사용 되는 모든 변수는 [개인](../../../parallel/openmp/reference/private-openmp.md), [공유](../../../parallel/openmp/reference/shared-openmp.md), [감소](../../../parallel/openmp/reference/reduction.md), [firstprivate](../../../parallel/openmp/reference/firstprivate.md), 또는 [lastprivate](../../../parallel/openmp/reference/lastprivate.md) 절 사용 하면 컴파일러 오류가 발생 합니다.  
  
 `default` 다음과 같은 지시문에 적용 됩니다.  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [섹션](../../../parallel/openmp/reference/sections-openmp.md)  
  
 자세한 내용은 참조 [2.7.2.5 기본](../../../parallel/openmp/2-7-2-5-default.md)합니다.  
  
## <a name="example"></a>예제  
 참조 [개인](../../../parallel/openmp/reference/private-openmp.md) 사용 하는 예제에 대 한 `default`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [절](../../../parallel/openmp/reference/openmp-clauses.md)