---
title: omp_get_wtime | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_get_wtime
dev_langs: C++
helpviewer_keywords: omp_get_wtime OpenMP function
ms.assetid: c8dee105-ec1b-42e5-a6e3-edeedcf9854c
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b071564cc6c5059d8978d45f80ce3e008622ec2f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="ompgetwtime"></a>omp_get_wtime
특정 시점에서 경과 된 시간 (초)에서 값을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double omp_get_wtime( );  
```  
  
## <a name="return-value"></a>반환 값  
 일부 임의의 이지만 일관 된 지점에서 경과 된 시간 (초)에서 값을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 후속 비교 가능한 하기가 프로그램 실행 도중 해당 지점 일관 된 상태로 유지 됩니다.  
  
 자세한 내용은 참조 [3.3.1 omp_get_wtime 함수](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md)합니다.  
  
## <a name="example"></a>예제  
  
```  
// omp_get_wtime.cpp  
// compile with: /openmp  
#include "omp.h"  
#include <stdio.h>  
#include <windows.h>  
  
int main() {  
    double start = omp_get_wtime( );  
    Sleep(1000);  
    double end = omp_get_wtime( );  
    double wtick = omp_get_wtick( );  
  
    printf_s("start = %.16g\nend = %.16g\ndiff = %.16g\n",  
             start, end, end - start);  
  
    printf_s("wtick = %.16g\n1/wtick = %.16g\n",  
             wtick, 1.0 / wtick);  
}  
```  
  
```Output  
start = 594255.3671159324  
end = 594256.3664474116  
diff = 0.9993314791936427  
wtick = 2.793651148400146e-007  
1/wtick = 3579545  
```  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../../parallel/openmp/reference/openmp-functions.md)