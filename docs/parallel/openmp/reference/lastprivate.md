---
title: lastprivate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- lastprivate
dev_langs:
- C++
helpviewer_keywords:
- lastprivate OpenMP clause
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7945edb879d81bb50753619c1206b9da575dbcda
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="lastprivate"></a>lastprivate
변수는 바깥쪽 컨텍스트에서 버전 개인 버전 최종 반복 (루프에 대 한 구문) 또는 마지막 섹션 (#pragma 섹션) 스레드가 실행의 같음 설정 되도록 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
lastprivate(var)  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `var`  
 어떤 스레드가 실행 하는 최종 반복 (루프에 대 한 구문) 또는 마지막 섹션 (#pragma 섹션)의 개인 버전으로 설정 하는 변수입니다.  
  
## <a name="remarks"></a>설명  
 `lastprivate` 다음과 같은 지시문에 적용 됩니다.  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 자세한 내용은 참조 [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md)합니다.  
  
## <a name="example"></a>예  
 참조 [일정](../../../parallel/openmp/reference/schedule.md) 사용 하는 예제에 대 한 `lastprivate` 절.  
  
## <a name="see-also"></a>참고 항목  
 [절](../../../parallel/openmp/reference/openmp-clauses.md)