---
title: "컴파일러 오류 C3804 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3804
dev_langs:
- C++
helpviewer_keywords:
- C3804
ms.assetid: 7c4cda28-ec96-4d04-937b-36dbd9944722
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 01952fa59be1fe64d6c8b8c7392a09ab9ac327c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3804"></a>컴파일러 오류 C3804
'property_accessor': 접근자 메서드에 속성 수행 해야 할 해서는 모두 static 이거나 모두 static  
  
 접근자 함수 정적 수 특수 속성을 정의할 때 또는 인스턴스를 하나만 있습니다.  
  
 자세한 내용은 [property](../../windows/property-cpp-component-extensions.md) 를 참조하세요.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3804 오류가 발생 합니다.  
  
```  
// C3804.cpp  
// compile with: /c /clr  
ref struct A {  
  
   property int i {  
      static int get() {}  
      void set(int i) {}  
   }   // C3804 error  
  
   // OK  
   property int j {  
      int get() { return 0; }  
      void set(int i) {}  
   }  
  
   property int k {  
      static int get() { return 0; }  
      static void set(int i) {}  
   }  
};  
```