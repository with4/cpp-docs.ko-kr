---
title: 컴파일러 오류 C3255 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3255
dev_langs:
- C++
helpviewer_keywords:
- C3255
ms.assetid: 877ffca2-fd92-44b6-9060-6091b928b1c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 740deb9a2981839a12d2570328369daf741a8da9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3255"></a>컴파일러 오류 C3255
'값 유형':이 값 형식 개체를 네이티브 힙에 동적으로 할당할 수 없습니다  
  
 값 형식 인스턴스의 (참조 [클래스 및 구조체](../../windows/classes-and-structs-cpp-component-extensions.md)) 관리 되는 멤버를 포함 하는 힙에 스택에 만들 수 있습니다.  
  
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
