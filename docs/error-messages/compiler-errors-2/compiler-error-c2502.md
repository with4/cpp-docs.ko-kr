---
title: "컴파일러 오류 C2502 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2502
dev_langs: C++
helpviewer_keywords: C2502
ms.assetid: affa0b86-15fc-4e17-b7f2-6aad4a3771c4
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 396ec843c03843b506174308a5b548f50379c06f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2502"></a>컴파일러 오류 C2502
'identifier': 기본 클래스에 너무 많은 액세스 한정자  
  
 기본 클래스에 대 한 액세스 한정자가 두 개 이상 있습니다. 하나의 액세스 한정자 (`public`, `private`, 또는 `protected`) ï ´ ù.  
  
 다음 샘플에서는 C2502 오류가 생성 됩니다.  
  
```  
// C2502.cpp  
// compile with: /c  
class A { };  
class B { };  
class C : private public A { };   // C2502  
  
// OK  
class D : private A {};  
class E : public A, private B {};  
```