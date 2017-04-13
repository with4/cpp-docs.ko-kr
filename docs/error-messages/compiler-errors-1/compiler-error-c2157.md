---
title: "컴파일러 오류 C2157 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 152b55fb228d73b03df615fd336e40e984521432
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2157"></a>컴파일러 오류 C2157
'function': pragma 목록에서 사용하려면 먼저 선언해야 합니다.  
  
 함수 이름에 대 한 함수 목록에서 참조 되기 전에 선언 되지 않은 한 [alloc_text](../../preprocessor/alloc-text.md) pragma입니다.  
  
 다음 샘플에서는 C2157을 생성합니다.  
  
```  
// C2157.cpp  
// compile with: /c  
#pragma alloc_text( "func", func)   // C2157  
  
// OK  
extern "C" void func();  
#pragma alloc_text( "func", func)  
```
