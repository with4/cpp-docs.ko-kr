---
title: "컴파일러 오류 C2533 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2533
dev_langs:
- C++
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c023fb47b0e2653cd7bf13b188b907558573a0ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2533"></a>컴파일러 오류 C2533
'identifier': 생성자에서 반환 형식을 사용할 수 없습니다.  
  
 생성자는 반환 형식을 가질 수 없으며, `void` 반환 형식도 가질 수 없습니다.  
  
 이 오류의 일반적인 출처는 클래스 정의의 끝과 첫 번째 생성자 구현 사이에 누락된 세미콜론입니다. 컴파일러는 생성자 함수에 대한 반환 형식의 정의로 클래스를 인식하고 C2533을 생성합니다.  
  
 다음 샘플에서는 C2533을 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2533.cpp  
// compile with: /c  
class X {  
public:  
   X();     
};  
  
int X::X() {}   // C2533 - constructor return type not allowed  
X::X() {}   // OK - fix by using no return type  
```