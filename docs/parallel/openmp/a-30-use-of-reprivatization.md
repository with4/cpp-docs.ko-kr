---
title: A. 30 Reprivatization 사용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 26529090-6c39-40f2-b806-e12374d6b5f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6026bba31fcc0db4e28ced14b3e847ac0cf8bf58
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689612"
---
# <a name="a30---use-of-reprivatization"></a>A.30   재전용화 사용
다음 예제에서는 변수 reprivatization 보여 줍니다. Private 변수를 표시할 수 있습니다 `private` 중첩 된 지시문에서 다시 합니다. 병렬 영역 바깥쪽에서 공유할 수 필요가 없습니다.  
  
```  
int i, a;  
...  
#pragma omp parallel private(a)  
{  
  ...  
  #pragma omp parallel for private(a)  
  for (i=0; i<10; i++)  
     {  
       ...  
     }  
}  
```