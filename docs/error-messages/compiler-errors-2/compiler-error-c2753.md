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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76643c0487cbc2487449df70da91dc74e21121f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2753"></a>컴파일러 오류 C2753
'*템플릿*': 부분 특수화는 기본 서식 파일에 대 한 인수 목록을 일치할 수 없습니다.  
  
 템플릿 인수 목록에 매개 변수 목록과 일치 하는 경우 컴파일러는 동일한 템플릿으로 간주 됩니다. 같은 서식 파일을 두 번 정의 허용 되지 않습니다.  
  
## <a name="example"></a>예
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