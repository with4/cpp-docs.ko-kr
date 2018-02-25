---
title: OMP_NESTED | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- OMP_NESTED
dev_langs:
- C++
helpviewer_keywords:
- OMP_NESTED OpenMP environment variable
ms.assetid: c43f5287-a548-40d0-bd54-0c6b2b9f9a53
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 363a125cb7f9858b1ef4105234344d2a8d35b707
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
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
  
## <a name="example"></a>예  
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