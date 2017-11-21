---
title: "컴파일러 오류 C2969 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2969
dev_langs: C++
helpviewer_keywords: C2969
ms.assetid: e4ea3d66-b937-4b2c-b42a-96e03fb11579
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fbb6606e3e0b6a007574dde7ec1f012cbb49a841
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2969"></a>컴파일러 오류 C2969
구문 오류: 'symbol': 멤버 함수 정의가 '}'로 끝나야 합니다.  
  
 템플릿 멤버 함수 정의에 짝이 맞지 않는 닫는 중괄호가 있습니다.  
  
 다음 샘플에서는 C2969를 생성합니다.  
  
```  
// C2969.cpp  
// compile with: /c  
class A {  
   int i;  
public:  
   A(int i) {}  
};  
  
A anA(1);  
  
class B {  
   A a;  
   B() : a(anA);   // C2969  
   // try the following line instead  
   // B() : a(anA) {}  
};  
```