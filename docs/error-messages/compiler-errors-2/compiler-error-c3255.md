---
title: "컴파일러 오류 C3255 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3255
dev_langs:
- C++
helpviewer_keywords:
- C3255
ms.assetid: 877ffca2-fd92-44b6-9060-6091b928b1c1
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 2739be65060cabd5e40fb0156c44aca23f0b7dcc
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3255"></a>컴파일러 오류 C3255
'value type': 네이티브 힙에이 값 형식 개체를 동적으로 할당할 수 없습니다  
  
 값 형식의 인스턴스 (참조 [클래스 및 구조체](../../windows/classes-and-structs-cpp-component-extensions.md)) 관리 되는 멤버를 포함 하는 만들 수는 힙에 있지만 스택에 합니다.  
  
 다음 샘플에서는 C3255 오류가 생성 됩니다.  
  
```  
// C3255.cpp  
// compile with: /clr  
using namespace System;  
value struct V {  
   Object^ o;  
};  
  
value struct V2 {  
   int i;  
};  
  
int main() {  
   V* pv = new V;   // C3255  
   V2* pv2 = new V2;  
   V v2;  
}  
```  

