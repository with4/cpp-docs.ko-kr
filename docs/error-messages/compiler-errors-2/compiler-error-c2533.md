---
title: 컴파일러 오류 C2533 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2533
dev_langs:
- C++
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06733dc8ee52462ab7fcac4255ee8fa697a9bac4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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