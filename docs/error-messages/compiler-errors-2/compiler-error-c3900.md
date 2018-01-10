---
title: "컴파일러 오류 C3900 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3900
dev_langs: C++
helpviewer_keywords: C3900
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e7d85041e90584822397302c39a1050fb59b2b34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3900"></a>컴파일러 오류 C3900
'member': 현재 범위에 사용할 수 없습니다  
  
 속성 블록에는 함수 선언 및 인라인 함수 정의 포함 될 수 있습니다. 멤버 함수 밖에 없습니다 속성 블록에서 허용 됩니다. 없음 typedef, 연산자 또는 friend 함수를 사용할 수 있습니다. 자세한 내용은 [property](../../windows/property-cpp-component-extensions.md)을 참조하세요.  
  
 액세스 방법 및 함수에만 이벤트 정의 포함할 수 있습니다.  
  
 다음 샘플에서는 C3900 오류가 생성 됩니다.  
  
```  
// C3900.cpp  
// compile with: /clr  
ref class X {  
   property int P {  
      void set(int);   // OK  
      int i;   // C3900 variable declaration  
   };  
};  
```  
  
 다음 샘플에서는 C3900 오류가 생성 됩니다.  
  
```  
// C3900b.cpp  
// compile with: /clr  
using namespace System;  
delegate void H();  
ref class X {  
   event H^ E {  
      int m;   // C3900  
  
      // OK  
      void Test() {}  
  
      void add( H^ h ) {}  
      void remove( H^ h ) {}  
      void raise( ) {}  
   }  
};  
```