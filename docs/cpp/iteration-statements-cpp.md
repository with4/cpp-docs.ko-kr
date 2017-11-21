---
title: "반복 문 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- iteration statements
- loop structures, iteration statements
ms.assetid: bf6d75f7-ead2-426a-9c47-33847f59b8c7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f81ffa2e6b8f1dc07e409b737f76cb8e6aca5258
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="iteration-statements-c"></a>반복 문 (C++)
반복 문을 사용하면 루프 종료 조건에 따라 문(또는 복합 문)이 0회 이상 실행됩니다. 경우는 제외의 순서를 실행 하는 경우이 명령문은 복합 문, 중 하나는 [나누기](../cpp/break-statement-cpp.md) 문 또는 [계속](../cpp/continue-statement-cpp.md) 문이 합니다.  
  
 C + +에서는 네 가지 반복 문을- [동안](../cpp/while-statement-cpp.md), [않습니다](../cpp/do-while-statement-cpp.md), [에 대 한](../cpp/for-statement-cpp.md), 및 [범위 기반 for](../cpp/range-based-for-statement-cpp.md)합니다. 루프 종료 해야 하거나 종료 식이 0 (false)으로 계산 될 때까지 반복 하는 이러한 각는 **나누기** 문. 다음 표에는 이러한 문과 해당 작업이 요약되어 있습니다. 각 문에 대해서는 뒤에 나오는 단원에서 자세히 설명합니다.  
  
### <a name="iteration-statements"></a>반복 문  
  
|문|평가 위치|초기화|증가|  
|---------------|------------------|--------------------|---------------|  
|`while`|루프의 맨 위|아니요|아니요|  
|**do**|루프의 맨 아래|아니요|아니요|  
|**for**|루프의 맨 위|예|예|  
|**범위 기반 for**|루프의 맨 위|예|예|  
  
 반복 문의 문 부분은 선언일 수 없지만, 선언을 포함하는 복합 문일 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++ 문 개요](../cpp/overview-of-cpp-statements.md)