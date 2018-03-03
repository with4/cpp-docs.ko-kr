---
title: "개인 절과 함께 범위 지정 변수 A.21 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 7cdb4a7f-af24-44ac-9d33-e43840bc8f3d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d05a124e0b872210d28ed35fcd90872e0c051eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="a21---scoping-variables-with-the-private-clause"></a>A.21   private 절을 사용하여 변수에 범위 지정
값 `i` 및 `j` 다음 예제에서 정의 되어 있지 않습니다 병렬 영역에서 종료 시:  
  
```  
int i, j;  
i = 1;  
j = 2;  
#pragma omp parallel private(i) firstprivate(j)  
{  
  i = 3;  
  j = j + 2;  
}  
printf_s("%d %d\n", i, j);  
```  
  
 대 한 자세한 내용은 `private` 절 참조 [섹션 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) 페이지 25입니다.