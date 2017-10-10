---
title: "컴파일러 오류 C2753 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2753
dev_langs:
- C++
helpviewer_keywords:
- C2753
ms.assetid: 92bfeeac-524a-4a8e-9a4f-fb8269055826
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: bd852023fe4e8cf9b1845ed1a4d53f937b039211
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2753"></a>컴파일러 오류 C2753
'*템플릿*': 부분 특수화는 기본 서식 파일에 대 한 인수 목록을 일치할 수 없습니다.  
  
 템플릿 인수 목록에 매개 변수 목록과 일치 하는 경우 컴파일러는 동일한 템플릿으로 간주 됩니다. 같은 서식 파일을 두 번 정의 허용 되지 않습니다.  
  
## <a name="example"></a>예제
 다음 샘플에서는 C2753 오류가 발생 하 고 해결 하는 방법을 보여줍니다.  
  
```cpp  
// C2753.cpp  
// compile with: cl /c C2753.cpp
template<class T>  
struct A {};  
  
template<class T>  
struct A<T> {};   // C2753  
// try the following line instead  
// struct A<int> {};  
  
template<class T, class U, class V, class W, class X>  
struct B {};  
```
