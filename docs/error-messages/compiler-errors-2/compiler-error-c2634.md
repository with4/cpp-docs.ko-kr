---
title: 컴파일러 오류 C2634 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2634
dev_langs:
- C++
helpviewer_keywords:
- C2634
ms.assetid: 58c8f2db-ac95-4a81-9355-ef3cfb0ba7b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 728bbb1a90a4c9d8095b1be1faf054fdec47bd9a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2634"></a>컴파일러 오류 C2634
'&class::member' : 참조 멤버에 대한 포인터가 잘못되었습니다.  
  
 참조 멤버에 대 한 포인터 선언 됩니다.  
  
 다음 샘플에서는 C2634 오류가 생성 됩니다.  
  
```  
// C2634.cpp  
int mem;  
struct S {  
   S() : rf(mem) { }  
   int &rf;  
};  
int (S::*pdm) = &S::rf;   // C2634  
```