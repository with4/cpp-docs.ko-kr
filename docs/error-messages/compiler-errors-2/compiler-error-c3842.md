---
title: "컴파일러 오류 C3842 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3842
dev_langs: C++
helpviewer_keywords: C3842
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ee13fc3bf1ecface79550ca8ccad2d45b8e4a03e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3842"></a>컴파일러 오류 C3842
'function': WinRT 또는 관리되는 형식의 멤버 함수에 'const' 및 'volatile' 한정자를 사용할 수 없습니다.  
  
 [const](../../cpp/const-cpp.md) 및 [휘발성](../../cpp/volatile-cpp.md) Windows 런타임 또는 관리 되는 형식 멤버 함수에서 지원 되지 않습니다.  
  
 다음 샘플에서는 C3842를 생성합니다.  
  
```  
// C3842a.cpp  
// compile with: /clr /c  
public ref struct A {  
   void f() const {}   // C3842  
   void f() volatile {}   // C3842  
  
   void f() {}  
};  
```