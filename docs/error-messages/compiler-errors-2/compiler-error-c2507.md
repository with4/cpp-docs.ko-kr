---
title: "컴파일러 오류 C2507 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2507
dev_langs:
- C++
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6320fd9b6642d6be36d59151dd9c3260917d1b61
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2507"></a>컴파일러 오류 C2507
'identifier': 기본 클래스에 가상 한정자가 너무 많은  
  
 클래스 또는 구조체로 선언 됨 `virtual` 두 번 이상. 하나의 `virtual` 한정자 목록에 기본 클래스의 각 클래스에 대해 표시할 수 있습니다.  
  
 다음 샘플에서는 C2507 오류가 생성 됩니다.  
  
```  
// C2507.cpp  
// compile with: /c  
class A {};  
class B : virtual virtual public A {};   // C2507  
class C : virtual public A {};   // OK  
```
