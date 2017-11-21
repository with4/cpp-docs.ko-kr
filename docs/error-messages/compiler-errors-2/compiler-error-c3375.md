---
title: "컴파일러 오류 C3375 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3375
dev_langs: C++
helpviewer_keywords: C3375
ms.assetid: f1df78c6-e6ca-48f3-8b29-4e1710002bf3
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8c5fc1af314d5c48149365ab77b4b0b3d9da4915
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3375"></a>컴파일러 오류 C3375
'function': 대리자 함수가 모호합니다.  
  
 대리자 인스턴스화가 정적 멤버 함수로 될 수 있습니다. 또는 바인딩되지 않은 대리자로서 인스턴스 함수가 될 수 있으므로 컴파일러에서 이 오류가 발생했습니다.  
  
 자세한 내용은 참조 [대리자 (c + + 구성 요소 확장명)](../../windows/delegate-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3375를 생성합니다.  
  
```  
// C3375.cpp  
// compile with: /clr  
ref struct R {  
   static void f(R^) {}  
   void f() {}  
};  
  
delegate void Del(R^);  
  
int main() {  
   Del ^ a = gcnew Del(&R::f);   // C3375  
}  
```