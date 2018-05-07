---
title: 컴파일러 오류 C3153 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3153
dev_langs:
- C++
helpviewer_keywords:
- C3153
ms.assetid: d775d97e-2480-484f-81f1-88406b10f947
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c9829313947c7d3e954ddfd309f47d571ae2639
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3153"></a>컴파일러 오류 C3153
'interface': 인터페이스의 인스턴스를 만들 수 없습니다  
  
 인터페이스를 인스턴스화할 수 없습니다. 인터페이스의 멤버를 사용 하려면 인터페이스에서 클래스를 파생 인터페이스 멤버를 구현 하 고 멤버를 사용 합니다.  
  
 다음 샘플에서는 C3153 오류가 생성 됩니다.  
  
```  
// C3153.cpp  
// compile with: /clr  
interface class A {  
};  
  
int main() {  
   A^ a = gcnew A;   // C3153  
}  
```  
