---
title: "식 문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e627e107df850f31a9cf04981795edd1185c0ce5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="expression-statement"></a>식 문
식 문을 사용하면 식이 계산됩니다. 식 문의 결과로 어떠한 제어 전송 또는 반복도 발생하지 않습니다.  
  
 식 문의 구문은 간단하게 다음과 같습니다.  
  
## <a name="syntax"></a>구문  
  
```  
[expression ] ;  
```  
  
## <a name="remarks"></a>설명  
 다음 문이 실행되기 전에 식 문의 모든 식이 계산되고 의도하지 않은 모든 결과가 완료됩니다. 가장 일반적인 식 문은 대입 및 함수 호출입니다.  단독 세미콜론 라고 하는 빈 식 문을 것으로 간주 됩니다 식이 선택 사항 이므로는 [null](../cpp/null-statement.md) 문.  
  
## <a name="see-also"></a>참고 항목  
 [C++ 문 개요](../cpp/overview-of-cpp-statements.md)