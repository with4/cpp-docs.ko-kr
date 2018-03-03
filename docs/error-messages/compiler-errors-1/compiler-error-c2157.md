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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 365218bccff744be577e5abf2a1472e40edccf7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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