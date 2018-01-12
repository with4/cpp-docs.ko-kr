---
title: "컴파일러 오류 C2754 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2754
dev_langs: C++
helpviewer_keywords: C2754
ms.assetid: 1cab66c5-da9d-4b81-b7fb-9cdc48ff1ccc
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 924867394629c4c8227c8f50f76a9d32cbb750e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2754"></a>컴파일러 오류 C2754
'specialization': 부분 특수화는 종속적 비형식 템플릿 매개 변수를 가질 수 없습니다  
  
 종속 된 비형식 템플릿 매개 변수를 가진 템플릿 클래스를 부분적으로 특수화할 하려고 했습니다. 이것은 허용되지 않습니다.  
  
 다음 샘플에서는 C2754 오류가 생성 됩니다.  
  
```  
// C2754.cpp  
// compile with: /c  
  
template<class T, T t>  
struct A {};  
  
template<class T, int N>  
struct B {};  
  
template<class T> struct A<T,5> {};   // C2754  
template<> struct A<int,5> {};   // OK  
template<class T> struct B<T,5> {};   // OK  
```