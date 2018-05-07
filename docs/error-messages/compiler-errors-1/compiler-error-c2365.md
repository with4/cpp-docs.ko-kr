---
title: 컴파일러 오류 C2365 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2365
dev_langs:
- C++
helpviewer_keywords:
- C2365
ms.assetid: 35839b0b-4055-4b79-8957-b3a0871bdd02
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 952d1ea71f0388b26d72e3cbdcb10185813242e2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2365"></a>컴파일러 오류 C2365
'class member': 재정의: 이전 정의는 'class member'입니다.  
  
 클래스 멤버를 다시 정의하려고 했습니다.  
  
 다음 샘플에서는 C2365를 생성합니다.  
  
```  
// C2365.cpp  
// compile with: /c  
class C1 {  
   int CFunc();  
   char *CFunc;   // C2365, already exists as a member function  
  
   int CMem;  
   char *CMem();   // C2365, already exists as a data member  
};  
```