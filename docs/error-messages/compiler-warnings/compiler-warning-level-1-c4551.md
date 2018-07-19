---
title: 컴파일러 경고 (수준 1) C4551 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4551
dev_langs:
- C++
helpviewer_keywords:
- C4551
ms.assetid: 458b59bd-e2d7-425f-9ba6-268ff200424f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 24ae77139e46e63946e4bb0402d3a697839d6fc8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276960"
---
# <a name="compiler-warning-level-1-c4551"></a>컴파일러 경고(수준 1) C4551
인수 목록이 없습니다. 함수 호출  
  
 함수 매개 변수를 사용 하는 경우에 함수 호출 함수 이름 뒤에 오는 괄호와 닫는 괄호를 포함 해야 합니다.  
  
 다음 샘플에서는 C4551 오류가 생성 됩니다.  
  
```  
// C4551.cpp  
// compile with: /W1  
void function1() {  
}  
  
int main() {  
   function1;   // C4551  
   function1();   // OK  
}  
```