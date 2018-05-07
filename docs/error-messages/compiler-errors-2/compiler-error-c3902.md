---
title: 컴파일러 오류 C3902 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3902
dev_langs:
- C++
helpviewer_keywords:
- C3902
ms.assetid: feb3bb29-f836-4d77-ba71-3876f7f4f216
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0430ab95ae4884c420a3f7153fbbbbc4f7931675
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3902"></a>컴파일러 오류 C3902
'accessor': 마지막 매개 변수 형식은 'type' 이어야 합니다.  
  
 하나 이상의 set 메서드의 마지막 매개 변수 형식의 속성의 형식과 일치 해야 합니다. 자세한 내용은 [property](../../windows/property-cpp-component-extensions.md)을 참조하세요.  
  
 다음 샘플에서는 C3902 오류가 생성 됩니다.  
  
```  
// C3902.cpp  
// compile with: /clr /c  
using namespace System;  
ref class X {  
   property String ^Name {  
      void set(int);   // C3902  
      // try the following line instead  
      // void set(String^){}  
   }  
  
   property double values[int,int] {  
      void set(int, int, float);   // C3902  
      // try the following line instead  
      // void set(int, int, double){}  
   }  
};  
```