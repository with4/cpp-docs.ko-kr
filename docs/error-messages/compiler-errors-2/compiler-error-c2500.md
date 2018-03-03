---
title: "컴파일러 오류 C2500 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2500
dev_langs:
- C++
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a7be7320c21469536f6ddada99abd862812d882
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2500"></a>컴파일러 오류 C2500
'identifier1': 'identifier2' 이미 직접 기본 클래스입니다.  
  
 클래스 또는 구조체의 기본 클래스 목록에 두 번 이상 나타납니다.  
  
 직접 기본에 기본 목록에 언급 된 하나입니다. 간접 기본은 기본 목록에 클래스 중 하나의 기본 클래스입니다.  
  
 클래스는 직접 기본 클래스를 두 번 이상 지정할 수 없습니다. 클래스는 두 번 이상 간접 기본 클래스도 사용할 수 있습니다.  
  
 다음 샘플에서는 C2500 오류가 생성 됩니다.  
  
```  
// C2500.cpp  
// compile with: /c  
class A {};  
class B : public A, public A {};    // C2500  
  
// OK  
class C : public A {};  
class D : public A {};  
class E : public C, public D {};  
```