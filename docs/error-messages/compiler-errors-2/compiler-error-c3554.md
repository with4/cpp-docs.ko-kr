---
title: 컴파일러 오류 C3554 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3554
dev_langs:
- C++
helpviewer_keywords:
- C3554
ms.assetid: aede18d5-fefc-4da9-9b69-adfe90bfa742
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4fb374e028097157ae72b621593a899af9fe2f91
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3554"></a>컴파일러 오류 C3554
'decltype'을 다른 형식 지정자와 함께 사용할 수 없습니다.  
  
 형식 지정자로 `decltype()` 키워드를 한정할 수는 없습니다. 예를 들어 다음 코드 조각은 C3554 오류를 생성합니다.  
  
```  
int x;  
unsigned decltype(x); // C3554  
```