---
title: "컴파일러 오류 C2929 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2929
dev_langs:
- C++
helpviewer_keywords:
- C2929
ms.assetid: 11134027-6adc-4733-b6bd-b94486bd1933
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 64842c40bb2e773bd3c935e0de3664943522e7b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2929"></a>컴파일러 오류 C2929
'identifier': 명시적 인스턴스화. 템플릿-클래스 멤버의 인스턴스화를 명시적으로 강제하고 억제할 수 없습니다.  
  
 인스턴스화되지 않도록 하는 동시에 식별자를 명시적으로 인스턴스화할 수 없습니다.  
  
 다음 샘플에서는 C2929를 생성합니다.  
  
```  
// C2929.cpp  
// compile with: /c  
template<typename T>  
class A {  
public:  
   A() {}  
};  
  
template A<int>::A();  
  
extern template A<int>::A();   // C2929  
```