---
title: "컴파일러 오류 C2391 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2391
dev_langs:
- C++
helpviewer_keywords:
- C2391
ms.assetid: 63a9c6b9-03cc-4517-885c-bdcd048643b3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 344febd6b849667e108f06d69c773bb656b16f61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2391"></a>컴파일러 오류 C2391
'identifier': 형식 정의 하는 동안 'friend'를 사용할 수 없습니다  
  
 `friend` 선언에는 완전 한 클래스 선언에 포함 됩니다. A `friend` 멤버 함수 또는 상세 형식 지정자, 하지만 완전 한 클래스 선언 하지 선언을 지정할 수 있습니다.  
  
 다음 샘플에서는 C2326을 생성합니다.  
  
```  
// C2391.cpp  
// compile with: /c  
class D {   
   void func( int );   
};  
  
class A {  
   friend class B { int i; };   // C2391  
  
   // OK  
   friend class C;  
   friend void D::func(int);  
};  
```