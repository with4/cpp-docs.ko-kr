---
title: "컴파일러 오류 C2811 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2811
dev_langs:
- C++
helpviewer_keywords:
- C2811
ms.assetid: 6a44b18e-44c1-49d8-9b99-e0545b9a6e7d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b5a8f38fecb6b139a8e36007affc1a394bd81254
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2811"></a>컴파일러 오류 C2811
'type1': ref 'type2'에서 상속할 수 없습니다는 ref 클래스 또는 인터페이스 클래스에서 클래스 에서만 상속할 수 있습니다  
  
 관리 되는 클래스에 대 한 관리 되지 않는 클래스를 기본 클래스로 사용 하려고 했습니다.  
  
 다음 샘플에서는 C2811 오류가 생성 됩니다.  
  
```  
// C2811.cpp  
// compile with: /clr /c  
struct S{};  
ref struct T {};  
ref class C : public S {};   // C2811  
ref class D : public T {};   // OK  
```
