---
title: "컴파일러 오류 C2723 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2723
dev_langs: C++
helpviewer_keywords: C2723
ms.assetid: 86925601-2297-4cfd-94e2-2caf27c474c4
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3816640569a503c8a56c4cf37f1bf23360b30a12
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2723"></a>컴파일러 오류 C2723
'function' : 함수 정의에는 'specifier' 지정자를 사용할 수 없습니다.  
  
 클래스 정의가 클래스 선언 외부에 있는 경우 지정자가 나타날 수 없습니다. `virtual` 지정자는 클래스 선언 내의 멤버 함수 선언에 대해서만 지정할 수 있습니다.  
  
 다음 샘플에서는 C2723 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2723.cpp  
struct X {  
   virtual void f();  
   virtual void g();  
};  
  
virtual void X::f() {}   // C2723  
  
// try the following line instead  
void X::g() {}  
```