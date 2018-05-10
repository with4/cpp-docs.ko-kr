---
title: Barrier 지시문의 A.20 바인딩 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a3fdcc26-6873-429b-998e-de451401483b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b1123ab0b4d406a613176dfcd50f459d089e45d9
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="a20---binding-of-barrier-directives"></a>A.20   barrier 지시문 바인딩
지시문 바인딩 규칙에 대 한 호출을 **장벽** 지시문을 가장 가까운 바깥쪽 바인딩할 `parallel` 지시문입니다. 지시문 바인딩에 대 한 자세한 내용은 참조 하십시오. [섹션 2.8](../../parallel/openmp/2-8-directive-binding.md) 페이지 32입니다.  
  
 다음 예제에서 호출 *주* 를 *sub2* 규격이 때문에 **장벽** (에서 *sub3*) 병렬 영역을 바인딩합니다 *sub2*합니다. 호출에서 *주* 를 *sub1* 규격이 때문에 **장벽** 서브루틴에 병렬 영역 바인딩됩니다 *sub2*합니다.  호출에서 *주* 를 *sub3* 규격이 때문에 **장벽** 병렬 영역에 바인딩되지 않습니다 되며이 무시 됩니다. 또한는 **장벽** 바깥쪽 병렬 영역에는 스레드 및에서 만든 모든 스레드 팀만 동기화 *sub1*합니다.  
  
```  
int main()  
{  
    sub1(2);  
    sub2(2);  
    sub3(2);  
}  
  
void sub1(int n)  
{  
    int i;  
    #pragma omp parallel private(i) shared(n)  
    {  
        #pragma omp for  
        for (i=0; i<n; i++)  
            sub2(i);  
    }  
}  
  
void sub2(int k)  
{  
     #pragma omp parallel shared(k)  
     sub3(k);  
}  
  
void sub3(int n)  
{  
    work(n);  
    #pragma omp barrier  
    work(n);  
}  
```