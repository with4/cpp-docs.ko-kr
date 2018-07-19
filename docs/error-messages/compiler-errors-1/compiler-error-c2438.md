---
title: 컴파일러 오류 C2438 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2438
dev_langs:
- C++
helpviewer_keywords:
- C2438
ms.assetid: 3a0ab3ba-d0e4-4d8f-971d-e503397cc827
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf42740c137953007cab2c5301bff122b553e5f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225540"
---
# <a name="compiler-error-c2438"></a>컴파일러 오류 C2438
'identifier': 생성자를 통해 정적 클래스 데이터를 초기화할 수 없습니다  
  
 클래스의 정적 멤버를 초기화 하는 생성자 사용 됩니다. 클래스 선언 외부 정의에서 정적 멤버를 초기화 합니다.  
  
 다음 샘플에서는 C2438 오류가 생성 됩니다.  
  
```  
// C2438.cpp  
struct X {  
   X(int i) : j(i) {}   // C2438  
   static int j;  
};  
  
int X::j;  
  
int main() {  
   X::j = 1;  
}  
```