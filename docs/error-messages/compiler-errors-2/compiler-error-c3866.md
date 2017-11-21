---
title: "컴파일러 오류 C3866 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3866
dev_langs: C++
helpviewer_keywords: C3866
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b1bcba6226a05379248a68f2047653333d98cdf8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3866"></a>컴파일러 오류 C3866
인수 목록이 없습니다. 함수 호출  
  
 비정적 멤버 함수 내에 소멸자 또는 종료자를 호출 하며 인수 목록의 아닙니다.  
  
 다음 샘플에서는 C3866 오류가 생성 됩니다.  
  
```  
// C3866.cpp  
// compile with: /c  
class C {  
   ~C();  
   void f() {  
      this->~C;   // C3866  
      this->~C();   // OK  
   }  
};  
```