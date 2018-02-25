---
title: OMP_SCHEDULE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- OMP_SCHEDULE
dev_langs:
- C++
helpviewer_keywords:
- OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2295a801-e584-4d2f-826f-7ca4c88846a6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ff09bf142fd1c8bbbd61d1e1d3bd76102f7d86b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ompschedule"></a>OMP_SCHEDULE
동작을 수정 하는 [일정](../../../parallel/openmp/reference/schedule.md) 절 때 `schedule(runtime)` 에 지정 된 한 `for` 또는 `parallel for` 지시문입니다.  
  
## <a name="syntax"></a>구문  
  
```  
set OMP_SCHEDULE[=type[,size]]  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `size`(선택 사항)  
 반복의 크기를 지정합니다. `size` 양의 정수 여야 합니다. 기본값은 1의 경우는 제외 `type` 는 정적입니다. 경우에 유효 하지 않은 `type` 은 `runtime`합니다.  
  
 `type`  
 일정의 종류:  
  
-   `dynamic`  
  
-   `guided`  
  
-   `runtime`  
  
-   `static`  
  
## <a name="remarks"></a>설명  
 OpenMP 표준의 Visual c + + 구현에서 기본값은 `OMP_SCHEDULE=static,0`합니다.  
  
 자세한 내용은 참조 [4.1 OMP_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md)합니다.  
  
## <a name="example"></a>예  
 다음 명령 집합의 **OMP_SCHEDULE** 환경 변수:  
  
```  
set OMP_SCHEDULE="guided,2"  
```  
  
 다음 명령은의 현재 설정을 표시는 **OMP_SCHEDULE** 환경 변수:  
  
```  
set OMP_SCHEDULE  
```  
  
## <a name="see-also"></a>참고 항목  
 [환경 변수](../../../parallel/openmp/reference/openmp-environment-variables.md)