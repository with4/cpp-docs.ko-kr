---
title: "컴파일러 오류 C2157 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2157
dev_langs:
- C++
helpviewer_keywords:
- C2157
ms.assetid: babbca24-16dc-4b69-be14-a675029249c1
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5735d0394be8114f2e0747e7e0d8dfefc84e580b
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2157"></a>컴파일러 오류 C2157
'function': pragma 목록에서 사용하려면 먼저 선언해야 합니다.  
  
 함수 이름이 선언되지 않은 상태에서 [alloc_text](../../preprocessor/alloc-text.md) pragma에 대한 함수 목록에서 참조되었습니다.  
  
 다음 샘플에서는 C2157을 생성합니다.  
  
```  
// C2157.cpp  
// compile with: /c  
#pragma alloc_text( "func", func)   // C2157  
  
// OK  
extern "C" void func();  
#pragma alloc_text( "func", func)  
```
