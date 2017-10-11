---
title: "컴파일러 오류 C2589 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2589
dev_langs:
- C++
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5301caf0b52e61000a804e1d73b76343a8b7b2eb
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2589"></a>컴파일러 오류 C2589
'identifier': 오른쪽에 잘못 된 토큰 ':: '  
  
 클래스, 구조체 또는 공용 구조체 이름은 범위 결정 연산자 (이중 콜론)의 왼쪽에 표시 하는 경우에 오른쪽에 토큰 클래스, 구조체 또는 공용 구조체 멤버 여야 합니다. 그렇지 않으면 전역 식별자 오른쪽에 나타날 수 있습니다.  
  
 범위 결정 연산자를 오버 로드할 수 없습니다.  
  
 다음 샘플에서는 C2589 오류가 생성 됩니다.  
  
```  
// C2589.cpp  
void Test(){}  
class A {};  
void operator :: ();   // C2589  
  
int main() {  
   ::Test();  
}  
```
