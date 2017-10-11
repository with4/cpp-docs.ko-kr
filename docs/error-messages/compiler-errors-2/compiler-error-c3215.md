---
title: "컴파일러 오류 C3215 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3215
dev_langs:
- C++
helpviewer_keywords:
- C3215
ms.assetid: d0d16007-8885-42e0-b086-2d3a61f348c5
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e4a649c01762b8a113e928bb63ffe293f86d21c3
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3215"></a>컴파일러 오류 C3215
'type1': 제네릭 형식 매개 변수가 이미 'type2'의 제약을 받습니다.  
  
 제약 조건을 두 번 이상 지정했습니다.  
  
 제네릭에 대한 자세한 내용은 [Generics](../../windows/generics-cpp-component-extensions.md)을 참조하세요.  
  
 다음 샘플에서는 C3215를 생성합니다.  
  
```  
// C3215.cpp  
// compile with: /clr  
interface struct A {};  
  
generic <class T>  
where T : A,A  
ref class C {};   // C3215  
```  
  
 해결 방법:  
  
```  
// C3215b.cpp  
// compile with: /clr /c  
interface struct A {};  
  
generic <class T>  
where T : A  
ref class C {};  
```
