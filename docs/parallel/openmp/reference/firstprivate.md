---
title: firstprivate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: firstprivate
dev_langs: C++
helpviewer_keywords: firstprivate OpenMP clause
ms.assetid: db479766-6d3b-4bbd-b28e-b192d826788c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0645eee74ab162c444531c141b297665653907b8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="firstprivate"></a>firstprivate
병렬 구문 하기 전에 존재 하기 때문에 각 스레드에 변수의 자체 인스턴스에 있어야 하 고 변수 값으로 변수를 초기화 해야 한다는 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
firstprivate(var)  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`var`|에 해당 하며 각 스레드는 인스턴스를 변수는 병렬 구문 하기 전에 존재 하기 때문에 변수를 값으로 초기화 됩니다. 둘 이상의 변수를 지정 하는 경우 변수 이름을 쉼표로 구분 합니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="remarks"></a>설명  
 `firstprivate`다음과 같은 지시문에 적용 됩니다.  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [섹션](../../../parallel/openmp/reference/sections-openmp.md)  
  
-   [single](../../../parallel/openmp/reference/single.md)  
  
 자세한 내용은 참조 [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md)합니다.  
  
## <a name="example"></a>예제  
 사용 하는 예제에 대 한 `firstprivate`의 예제를 참조 [개인](../../../parallel/openmp/reference/private-openmp.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [절](../../../parallel/openmp/reference/openmp-clauses.md)