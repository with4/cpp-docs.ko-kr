---
title: 컴파일러 오류 C2041 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2041
dev_langs:
- C++
helpviewer_keywords:
- C2041
ms.assetid: c9a33bb1-f9cf-47d6-bd21-7d867a8c37d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 747dd5621aec556e89fee2ab8e7ff512736e408c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164468"
---
# <a name="compiler-error-c2041"></a>컴파일러 오류 C2041
'character' 기본 'number'에 대 한 잘못 된 자릿수  
  
 지정 된 문자 (예: 8 진수 또는 16 진수) 자료에 유효한 숫자가 아닌 경우  
  
 다음 샘플에서는 C2041 오류가 생성 됩니다.  
  
```  
// C2041.cpp  
int i = 081;   // C2041  8 is not a base 8 digit  
```  
  
 해결 방법:  
  
```  
// C2041b.cpp  
// compile with: /c  
int j = 071;  
```