---
title: omp_get_nested | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_get_nested
dev_langs: C++
helpviewer_keywords: omp_get_nested OpenMP function
ms.assetid: e9784847-516e-40d3-89f7-b8b6898d8667
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 557625a40707119633adc1d73775b1e66f67efec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ompgetnested"></a>omp_get_nested
중첩 된 병렬 처리를 사용할 수 있는지 여부를 나타내는 값을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int omp_get_nested( );  
```  
  
## <a name="return-value"></a>반환 값  
 0이 아닌 경우 중첩 된 병렬 처리를 사용 합니다.  
  
## <a name="remarks"></a>설명  
 중첩 된 병렬 처리 수준으로 지정 된 [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) 및 [OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md)합니다.  
  
 자세한 내용은 참조 [3.1.10 omp_get_nested 함수](../../../parallel/openmp/3-1-10-omp-get-nested-function.md)합니다.  
  
## <a name="example"></a>예  
 참조 [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) 사용 하는 예제에 대 한 `omp_get_nested`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../../parallel/openmp/reference/openmp-functions.md)