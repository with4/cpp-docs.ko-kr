---
title: 컴파일러 오류 C3553 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3553
dev_langs:
- C++
helpviewer_keywords:
- C3553
ms.assetid: 7f84bf37-6419-4ad3-ab30-64266100b930
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a4ed8c2776015f9d9c6aedbe7a9da93f404f680
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3553"></a>컴파일러 오류 C3553
decltype에 형식이 아니라 식이 필요합니다.  
  
 `decltype()` 키워드는 형식 이름이 아니다를 인수로 식을 사용하도록 요구합니다. 예를 들어 다음 코드 조각의 마지막 문은 C3553 오류를 생성합니다.  
  
 `int x = 0;`  
  
 `decltype(x+1);`  
  
 `decltype(int); // C3553`