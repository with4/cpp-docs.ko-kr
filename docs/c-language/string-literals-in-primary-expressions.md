---
title: "기본 식의 문자열 리터럴 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- string literals, in primary expressions
ms.assetid: 3ec31278-527b-40d2-8c83-6b09e2d81ca6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0920280f672b1c45d317ade4c592a6b93356fb8f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="string-literals-in-primary-expressions"></a>기본 식의 문자열 리터럴
"문자열 리터럴"은 문자, 와이드 문자 또는 큰따옴표로 묶은 인접 문자의 시퀀스입니다. 이는 변수가 아니므로 문자열 리터럴 및 해당 요소 중 어느 것도 할당 연산에서 왼쪽 피연산자일 수 없습니다. 문자열 리터럴의 형식은 `char`의 배열(또는 와이드 문자열 리터럴에 대한 `wchar_t`의 배열)입니다. 식의 배열은 포인터로 변환됩니다. 문자열에 대한 자세한 내용은 [문자열 리터럴](../c-language/c-string-literals.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [C 기본 식](../c-language/c-primary-expressions.md)