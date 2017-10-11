---
title: "컴파일러 오류 C2014 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2014
dev_langs:
- C++
helpviewer_keywords:
- C2014
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a4c6a3cc07b28e5636e61769b6dce0760938c591
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

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
