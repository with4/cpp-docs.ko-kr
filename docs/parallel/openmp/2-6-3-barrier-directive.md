---
title: 2.6.3 barrier 지시문 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68df92207feb45a77055098cdb1227a68b04bcab
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689794"
---
# <a name="263-barrier-directive"></a>2.6.3 barrier 지시문
**장벽** 지시문 팀의 모든 스레드를 동기화 합니다. 오류가 발생 하면 팀에서 각 스레드에이 점에 도달해 서는 다른 모든 때까지 기다립니다. 구문은 **장벽** 지시문은 다음과 같습니다.  
  
```  
#pragma omp barrier new-line  
```  
  
 팀의 모든 스레드가 장벽 발생 했을 팀의 각 스레드에서 문을 병렬로 barrier 지시문 뒤에 실행을 시작 합니다. 되므로 **장벽** 지시문은 C 언어 문 구문의 일환으로, 프로그램에서의 위치에 몇 가지 제한이 있습니다. 참조 [부록 C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) 정식 문법에 대 한 합니다. 다음 예제에서는 이러한 제한 사항을 보여 줍니다.  
  
```  
/* ERROR - The barrier directive cannot be the immediate  
*          substatement of an if statement  
*/  
if (x!=0)  
   #pragma omp barrier  
...  
  
/* OK - The barrier directive is enclosed in a  
*      compound statement.  
*/  
if (x!=0) {  
   #pragma omp barrier  
}  
```