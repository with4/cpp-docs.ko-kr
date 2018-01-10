---
title: "컴파일러 경고 (수준 1) C4946 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4946
dev_langs: C++
helpviewer_keywords: C4946
ms.assetid: b85cbef0-e053-4de6-9b14-7b0f82d40495
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 800d940c3005762bddf6402a14af4416da4bc50e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4946"></a>컴파일러 경고(수준 1) C4946
관련 클래스 'class1'과(와) 'class2' 사이에 reinterpret_cast가 사용되었습니다.  
  
 사용 하지 마십시오 [reinterpret_cast](../../cpp/reinterpret-cast-operator.md) 관련된 형식 간에 캐스팅 합니다. 사용 하 여 [static_cast](../../cpp/static-cast-operator.md) 대신 나 다형 형식을 사용 하 여 [dynamic_cast](../../cpp/dynamic-cast-operator.md)합니다.  
  
 기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)을 참조하세요.  
  
 다음 코드 예제에서는 C4946이 생성됩니다.  
  
```  
// C4946.cpp  
// compile with: /W1  
#pragma warning (default : 4946)  
class a {  
public:  
   a() : m(0) {}  
   int m;  
};  
  
class b : public virtual a {  
};  
  
class b2 : public virtual a {  
};  
  
class c : public b, public b2 {  
};  
  
int main() {  
   c* pC = new c;  
   a* pA = reinterpret_cast<a*>(pC);   // C4946  
   // try the following line instead  
   // a* pA = static_cast<a*>(pC);  
}  
```