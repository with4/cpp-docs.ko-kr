---
title: 컴파일러 오류 C2589 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2589
dev_langs:
- C++
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c15589358979f554a9c17114f7d78b05dd83c472
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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