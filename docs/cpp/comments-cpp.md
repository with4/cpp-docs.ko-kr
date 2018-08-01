---
title: 주석 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- code comments, C++
- comments, documenting code
- comments, C++ code
- white space, C++ comments
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a412c2b4dd87bc3e8e3e1b77a524d2a5925aaf60
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405060"
---
# <a name="comments-c"></a>주석 (c + +)
메모는 프로그래머에 게 유용 하지만 컴파일러에서 무시 하는 텍스트입니다. 일반적으로 주석은 나중에 참조할 수에 대 한 코드에 주석을 사용 합니다. 컴파일러는 공백 처리 합니다. 비활성; 특정 코드 줄 수 있도록 주석을 테스트를 사용할 수 있습니다. 그러나 `#if` / `#endif` 전처리기 지시문에 더 적합 한이 주석이 포함 된 코드를 둘러쌀 수 있습니다 하지만 주석 중첩할 수 없습니다.  
  
 C + + 주석은 다음 방법 중 하나에 기록 됩니다.  
  
-   합니다 `/*` (슬래시, 별표) 뒤에 임의의 문자 시퀀스입니다 (줄 바꿈 포함) 뒤에 문자를 `*/` 문자입니다. 이 구문은 ANSI C.와 동일  
  
-   `//` (두 개의 슬래시) 문자를 뒤에 임의의 문자 시퀀스입니다. 즉시는 아닙니다 백슬래시 앞에 새 줄 주석의이 폼을 종료 합니다. 따라서 일반적으로 라고 "한 줄 주석"입니다.  
  
 주석 문자 (`/*`, `*/`, 및 `//`)가 문자 상수 내 문자열 리터럴 또는 주석 특별 한 의미가 없습니다. 따라서 첫 번째 구문을 사용 하 여 주석은 중첩할 수 없습니다.  
  
## <a name="see-also"></a>참고자료  
 [어휘 규칙](../cpp/lexical-conventions.md)