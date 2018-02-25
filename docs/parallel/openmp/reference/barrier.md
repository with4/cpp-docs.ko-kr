---
title: "장벽 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- barrier
dev_langs:
- C++
helpviewer_keywords:
- barrier OpenMP directive
ms.assetid: 5c73ad4f-c768-443a-8f9e-4fd8bc2253c7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0008c343130bf47170957204793cf3c85b22f1e3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="barrier"></a>barrier
팀;의 모든 스레드를 동기화합니다. 장벽, 모든 스레드는 장벽 실행 될 때까지 모든 스레드가 일시 중지 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#pragma omp barrier  
```  
  
## <a name="remarks"></a>설명  
 `barrier` 지시문 OpenMP 절을 지원 합니다.  
  
 자세한 내용은 참조 [2.6.3 barrier 지시문](../../../parallel/openmp/2-6-3-barrier-directive.md)합니다.  
  
## <a name="example"></a>예  
 샘플을 사용 하는 방법에 대 한 `barrier`, 참조 [마스터](../../../parallel/openmp/reference/master.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문](../../../parallel/openmp/reference/openmp-directives.md)