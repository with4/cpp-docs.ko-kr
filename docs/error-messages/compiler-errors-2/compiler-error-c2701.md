---
title: "컴파일러 오류 C2701 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2701
dev_langs: C++
helpviewer_keywords: C2701
ms.assetid: 31cf2ab7-ced9-4f75-aa51-e169e20407fb
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9aff17907695e48661af7d6e9a6538af4f22ba4c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2701"></a>컴파일러 오류 C2701
'function': 함수 템플릿을 지역 클래스의 friend 일 수 없습니다  
  
 지역 클래스 friend 함수로 템플릿 함수를 사용할 수 없습니다.  
  
 다음 샘플에서는 C2701 오류가 생성 됩니다.  
  
```  
// C2701.cpp  
// compile with: /c  
template<typename T>   // OK  
void f1(const T &);  
  
void MyFunction() {  
   class MyClass {  
      template<typename T> friend void f2(const T &);   // C2701  
   };  
}  
```