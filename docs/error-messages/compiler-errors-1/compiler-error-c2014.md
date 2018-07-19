---
title: 컴파일러 오류 C2014 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2014
dev_langs:
- C++
helpviewer_keywords:
- C2014
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 839fececb10897c799473ae328afb9f422b4c390
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33165963"
---
# <a name="compiler-error-c2014"></a>컴파일러 오류 C2014
전처리기 명령은 공백 아닌 문자로 시작 해야 합니다.  
  
 `#` 기호는 전처리기 지시문의 공백 없는 줄에 첫 번째 문자 여야 합니다.  
  
 다음 샘플에서는 C2014 오류가 생성 됩니다.  
  
```  
// C2014.cpp  
int k; #include <stdio.h>   // C2014  
```  
  
 해결 방법:  
  
```  
// C2014b.cpp  
// compile with: /c  
int k;   
#include <stdio.h>  
```