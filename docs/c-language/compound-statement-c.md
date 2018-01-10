---
title: "복합 문 (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- compound statements
- statements, compound
ms.assetid: 32d1bf86-cbbc-42a9-ba3a-1be1c6c7754c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9422e3229aa5e800859f50e1ca058e32a4120074
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compound-statement-c"></a>복합 문 (C)
"블록"이라고도 하는 복합 문은 일반적으로 **if** 문 같은 다른 문의 본문으로 나타납니다. [선언 및 형식](../c-language/declarations-and-types.md)에서는 복합 문 헤드에 나타날 수 있는 선언의 형태와 의미에 대해 설명합니다.  
  
## <a name="syntax"></a>구문  
 *compound-statement*:  
 **{**  *declaration-list* opt*statement-list*opt**}**  
  
 *declaration-list*:  
 *declaration*  
  
 *declaration-list declaration*  
  
 *statement-list*:  
 s*tatement*  
  
 *statement-list statement*  
  
 선언이 있을 경우 모든 문 앞에 와야 합니다. 복합 문의 시작 지점에 선언된 각 식별자의 범위는 블록의 끝 지점까지 확장됩니다. 내부 블록에 동일한 식별자의 선언이 없는 경우 블록 전체에 표시됩니다.  
  
 `extern`만 가능한 함수를 제외하고 **register**, **static** 또는 `extern`을 사용하여 명시적으로 선언되지 않은 복합 문의 식별자는 **auto**로 간주됩니다. 함수 선언에서 `extern` 지정자를 해제할 수 있으며 함수는 여전히 `extern`입니다.  
  
 복합 문에서 변수 또는 함수를 선언할 때 저장소 클래스 `extern`을 사용하지 않으면 저장소가 할당되지 않고 초기화가 허용되지 않습니다. 선언은 외부 변수나 다른 곳에서 정의된 함수를 참조합니다.  
  
 **auto** 또는 **register** 키워드를 사용하여 블록에서 선언된 변수는 다시 할당되고, 필요한 경우 복합 문이 시작될 때마다 초기화됩니다. 이 변수는 복합 문이 종료된 후에는 정의되지 않습니다. 블록 내부에서 선언된 변수에 **static** 특성이 있는 경우 프로그램 실행이 시작되고 프로그램 전체에 해당 값을 유지하면 변수가 초기화됩니다. **static**에 대한 자세한 내용은 [저장소 클래스](../c-language/c-storage-classes.md)를 참조하세요.  
  
 다음 예제는 복합 문에 대해 설명합니다.  
  
```  
if ( i > 0 )   
{  
    line[i] = x;  
    x++;  
    i--;  
}  
```  
  
 이 예제에서 `i`가 0보다 클 경우 복합 문 내부의 모든 문이 순서대로 실행됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [문](../c-language/statements-c.md)