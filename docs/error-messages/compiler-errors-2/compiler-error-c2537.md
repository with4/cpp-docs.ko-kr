---
title: "컴파일러 오류 C2537 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2537
dev_langs:
- C++
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 610fe53b68ccfa9f0ec187356a737e67837656a4
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2537"></a>컴파일러 오류 C2537
'specifier': 링크 사양이 올바르지 않습니다  
  
 가능한 원인:  
  
1.  링크 지정 자가 지원 되지 않습니다. "C" 링크 지정자만 사용할 수 있습니다.  
  
2.  "C" 링크가 둘 이상의 함수 오버 로드 된 함수 집합에 지정 됩니다. 이것은 허용되지 않습니다.  
  
 다음 샘플에서는 C2537 오류가 생성 됩니다.  
  
```  
// C2537.cpp  
// compile with: /c  
extern "c" void func();   // C2537  
extern "C" void func2();   // OK  
```
