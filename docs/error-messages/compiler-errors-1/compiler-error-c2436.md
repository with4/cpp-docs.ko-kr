---
title: "컴파일러 오류 C2436 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2436
dev_langs:
- C++
helpviewer_keywords:
- C2436
ms.assetid: ca4cc813-bc1d-4c0a-9a2c-3a5fe673d084
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ca31514bc53a134be4b327c175b049d258e07682
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2436"></a>컴파일러 오류 C2436
'identifier': 멤버 함수 또는 생성자 이니셜라이저 목록에서 중첩된 클래스  
  
 멤버 함수 또는 생성자 이니셜라이저 목록에는 지역 클래스를 초기화할 수 없습니다.  
  
 다음 샘플에서는 C2436 오류가 생성 됩니다.  
  
```  
// C2436.cpp  
struct S{  
   int f();  
   struct Inner{  
      int i;  
   };  
   S():f(10), Inner(0){}   // C2436  
};  
```