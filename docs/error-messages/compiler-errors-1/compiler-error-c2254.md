---
title: "컴파일러 오류 C2254 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2254
dev_langs: C++
helpviewer_keywords: C2254
ms.assetid: 49bb3d7e-3bdf-4af6-937c-fa627be412a9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 388d14e4e2d68f2eefc701f6156e27dda4cb9aa0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2254"></a>컴파일러 오류 C2254
'function': 순수 지정자 또는 추상 재정의 지정자는 friend 함수에 사용할 수 없습니다  
  
 A `friend` 함수가 순수으로 지정 된 `virtual`합니다.  
  
 다음 샘플에서는 C2254 오류가 생성 됩니다.  
  
```  
// C2254.cpp  
// compile with: /c  
class A {  
public:  
   friend void func1() = 0;   // C2254, func1 is friend  
   void virtual func2() = 0;   // OK, pure virtual  
   friend void func3();   // OK, friend not virtual nor pure  
};  
  
void func1() {};  
void func3() {};  
```