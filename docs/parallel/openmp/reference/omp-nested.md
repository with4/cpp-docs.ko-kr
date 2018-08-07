---
title: OMP_NESTED | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_NESTED
dev_langs:
- C++
helpviewer_keywords:
- OMP_NESTED OpenMP environment variable
ms.assetid: c43f5287-a548-40d0-bd54-0c6b2b9f9a53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6b51df88ae700f81cf84250cc06ae24c9131fec
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691224"
---
# <a name="ompnested"></a>OMP_NESTED
중첩 된 병렬 처리 하지 않을 지와 사용 하지 않도록 설정 하지 않으면 중첩 된 병렬 처리는 활성화 여부를 지정 `omp_set_nested`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
set OMP_NESTED[=TRUE | =FALSE]  
```  
  
## <a name="remarks"></a>설명  
 `OMP_NESTED` 환경 변수 재정의 될 수 있습니다는 [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) 함수입니다.  
  
 OpenMP 표준의 Visual c + + 구현에서 기본값은 `OMP_DYNAMIC=FALSE`합니다.  
  
 자세한 내용은 참조 [4.4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md)합니다.  
  
## <a name="example"></a>예제  
 다음 명령 집합의 `OMP_NESTED` 환경 변수를 true로:  
  
```  
set OMP_NESTED=TRUE  
```  
  
 다음 명령은의 현재 설정을 표시는 `OMP_NESTED` 환경 변수:  
  
```  
set OMP_NESTED  
```  
  
## <a name="see-also"></a>참고 항목  
 [환경 변수](../../../parallel/openmp/reference/openmp-environment-variables.md)