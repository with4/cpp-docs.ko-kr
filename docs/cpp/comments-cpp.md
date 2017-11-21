---
title: "주석 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- code comments, C++
- comments, documenting code
- comments, C++ code
- white space, C++ comments
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 828d02ddd02c7484e142333bdb87453f8fb922e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="comments-c"></a>주석 (c + +)
메모는 프로그래머에 게 유용 하지만 컴파일러에서 무시 하는 텍스트입니다. 주석은 나중에 참조할 수는 코드 주석을 추가 하려면 일반적으로 사용 됩니다. 컴파일러는 흰 공간으로 처리 합니다. 어떤 코드 줄을 비활성; 있도록 주석을 테스트를 사용할 수 있습니다. 그러나 `#if` / `#endif` 전처리기 지시문 더 잘 작동이 대 한 설명을 포함 하는 코드를 둘러쌀 수 되었지만 메모를 중첩할 수 없습니다.  
  
 C + + 주석 다음 방법 중 하나에 작성 됩니다.  
  
-   `/*` (슬래시, 별표) 문자 다음에 옵니다 (줄 바꿈은 포함) 문자의 시퀀스는 `*/` 문자입니다. 이 구문은 ANSI C.와 동일  
  
-   `//` (두 개의 슬래시) 문자를 뒤에 일련의 문자입니다. 즉시는 아닙니다 백슬래시가 앞에 새 줄이 주석이 형식을 종료 합니다. 따라서 일반적으로 라고 "한 줄 주석"입니다.  
  
 주석 문자 (`/*`, `*/`, 및 `//`)가 내 문자 상수, 리터럴, 문자열 또는 주석 특별 한 의미가 없습니다. 따라서 첫 번째 구문을 사용 하 여 메모는 중첩할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [어휘 규칙](../cpp/lexical-conventions.md)