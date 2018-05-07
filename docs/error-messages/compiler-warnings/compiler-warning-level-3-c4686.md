---
title: 컴파일러 경고 (수준 3) C4686 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4686
dev_langs:
- C++
helpviewer_keywords:
- C4686
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1edbf438951644f63aae637a68f69d173ab7e1b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4686"></a>컴파일러 경고(수준 3) C4686
**'**   
 ***사용자 정의 형식* ': 동작 변경 되었을 수, udt 반환 호출 규칙이**  
  
 클래스 템플릿 특수화 않은 반환 형식에 사용 되기 전에 정의 됩니다. C4686; 확인 되는 클래스를 인스턴스화하는 모든 항목 인스턴스를 선언 하거나 멤버 액세스 (C\<int >:: 아무 것도) 하는 옵션도 있습니다.  
  
 기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.  
  
 대신, 다음을 시도합니다  
  
```  
// C4686.cpp  
// compile with: /W3  
#pragma warning (default : 4686)  
template <class T>  
class C;  
  
template <class T>  
C<T> f(T);  
  
template <class T>  
class C {};  
  
int main() {  
   f(1);   // C4686  
}  
  
template <class T>  
C<T> f(T) {  
   return C<int>();  
}  
```