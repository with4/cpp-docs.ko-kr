---
title: 반복 문 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- iteration statements
- loop structures, iteration statements
ms.assetid: bf6d75f7-ead2-426a-9c47-33847f59b8c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 988d46b3f4b2e20ff14227fda70a6f39ac95756c
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402899"
---
# <a name="iteration-statements-c"></a>반복 문 (C++)
반복 문을 사용하면 루프 종료 조건에 따라 문(또는 복합 문)이 0회 이상 실행됩니다. 경우를 제외 하 고 순서 대로 실행 됩니다 이러한 문이 복합 문 경우 중 하나는 [나누기](../cpp/break-statement-cpp.md) 문 또는 [계속](../cpp/continue-statement-cpp.md) 문이 합니다.  
  
 C + +는 네 가지 반복 문을 제공 — [하는 동안](../cpp/while-statement-cpp.md), [수행](../cpp/do-while-statement-cpp.md)를 [에 대 한](../cpp/for-statement-cpp.md), 및 [범위 기반 for](../cpp/range-based-for-statement-cpp.md)합니다. 0 (false)로 종료 식이 계산 될 때까지 또는 루프 종료는 강제 적용 될 때까지 반복 하는 이러한 각를 **중단** 문입니다. 다음 표에는 이러한 문과 해당 작업이 요약되어 있습니다. 각 문에 대해서는 뒤에 나오는 단원에서 자세히 설명합니다.  
  
### <a name="iteration-statements"></a>반복 문  
  
|문|평가 위치|초기화|증가|  
|---------------|------------------|--------------------|---------------|  
|**while**|루프의 맨 위|아니요|아니요|  
|**do**|루프의 맨 아래|아니요|아니요|  
|**for**|루프의 맨 위|예|예|  
|**범위 기반 for**|루프의 맨 위|예|예|  
  
 반복 문의 문 부분은 선언일 수 없지만, 선언을 포함하는 복합 문일 수 있습니다.  
  
## <a name="see-also"></a>참고자료  
 [C++ 문 개요](../cpp/overview-of-cpp-statements.md)