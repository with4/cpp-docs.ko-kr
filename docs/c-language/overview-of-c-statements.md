---
title: C 문 개요 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- semicolon, in C statements
- statements, C
- semicolon
- statements, about statements
- Visual C, statements
ms.assetid: 0d49837a-5399-4881-b60c-af5f4e9720de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a3cf80e6237b21101f737f496eb39688ec6ed0a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="overview-of-c-statements"></a>C 문 개요
C 문은 토큰, 식 및 다른 문으로 구성되어 있습니다. 다른 문의 구성 요소를 형성하는 문을 바깥쪽 문의 "본문"이라고 합니다. 이 단원에서는 다음 구문에 지정된 각 문 형식에 대해 설명합니다.  
  
## <a name="syntax"></a>구문  
 *statement*:  
 [labeled-statement](../c-language/goto-and-labeled-statements-c.md)  
  
 [compound-statement](../c-language/compound-statement-c.md)  
  
 [expression-statement](../c-language/expression-statement-c.md)  
  
 [selection-statement](../c-language/if-statement-c.md)  
  
 [iteration-statement](../c-language/do-while-statement-c.md)  
  
 [jump-statement](../c-language/break-statement-c.md)  
  
 [try-except-statement](../c-language/try-except-statement-c.md)  
  
 /* Microsoft 전용 \*/[try-finally-statement](../c-language/try-finally-statement-c.md) /\* Microsoft 전용 \*/  
  
 대개 문 본문은 "복합 문"입니다. 복합 문은 키워드를 포함할 수 있는 다른 문으로 구성됩니다. 복합 문은 중괄호(**{ }**)로 구분됩니다. 다른 모든 C 문은 세미콜론(**;**)으로 끝납니다. 세미콜론은 문 종결자입니다.  
  
 식 문에는 [식 및 할당](../c-language/expressions-and-assignments.md)에 소개된 산술 연산자 또는 논리 연산자를 포함할 수 있는 C 식이 포함되어 있습니다. null 문은 빈 문입니다.  
  
 모든 C 문은 이름과 콜론으로 구성된 식별 레이블로 시작될 수 있습니다. `goto` 문은 레이블 문만 인식하므로 레이블 문에 대해서는 `goto`와 함께 설명합니다. 자세한 내용은 [goto 문 및 레이블 문](../c-language/goto-and-labeled-statements-c.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [문](../c-language/statements-c.md)