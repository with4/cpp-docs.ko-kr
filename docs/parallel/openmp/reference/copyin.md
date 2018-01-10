---
title: copyin | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: copyin
dev_langs: C++
helpviewer_keywords: copyin OpenMP clause
ms.assetid: 369efa88-613c-4cb1-9e11-7b9ee08a4b25
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3190c1f6914ae8ea24b968a8cf286de1867938cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="copyin"></a>copyin
스레드가 마스터 스레드에 값에 대 한 액세스를 허용 된 [threadprivate](../../../parallel/openmp/reference/threadprivate.md) 변수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
copyin(var)  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `var`  
 `threadprivate` 변수는 병렬 구문 하기 전에 있는 것 처럼 마스터 스레드에의 변수 값으로 초기화할 수입니다.  
  
## <a name="remarks"></a>설명  
 `copyin`다음과 같은 지시문에 적용 됩니다.  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [섹션](../../../parallel/openmp/reference/sections-openmp.md)  
  
 자세한 내용은 참조 [2.7.2.7 copyin](../../../parallel/openmp/2-7-2-7-copyin.md)합니다.  
  
## <a name="example"></a>예  
 참조 [threadprivate](../../../parallel/openmp/reference/threadprivate.md) 사용 하는 예제에 대 한 `copyin`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [절](../../../parallel/openmp/reference/openmp-clauses.md)