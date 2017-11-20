---
title: "컴파일러 오류 C3901 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3901
dev_langs: C++
helpviewer_keywords: C3901
ms.assetid: 19af4141-39ad-4c16-a68f-3ae76f648186
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 778bb3336d33c52ce0efcefe96d4da304c1502cf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3901"></a>컴파일러 오류 C3901
'accessor_function': 'type' 반환 형식이 있어야 합니다.  
  
 적어도 하나 이상의 get 메서드의 반환 형식이 속성 형식과 일치 해야 합니다. 자세한 내용은 [property](../../windows/property-cpp-component-extensions.md)을 참조하세요.  
  
 다음 샘플에서는 C3901 오류가 생성 됩니다.  
  
```  
// C3901.cpp  
// compile with: /clr /c  
using namespace System;  
ref class X {  
   property String^ Name {  
      void get();   // C3901  
      // try the following line instead  
      // String^ get();  
   };  
};  
  
ref class Y {  
   property double values[int, int] {  
      int get(int, int);   // C3901  
      // try the following line instead  
      // double get(int, int);  
   };  
};  
```