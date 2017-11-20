---
title: "컴파일러 오류 C2427 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2427
dev_langs: C++
helpviewer_keywords: C2427
ms.assetid: a7d421af-6180-40b4-b7a6-9f3bc7dfaaf9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 416db305963b6357c6dce9c5b2d13f0a6ca186f3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2427"></a>컴파일러 오류 C2427
'class':이 범위에서 클래스를 정의할 수 없습니다  
  
 중첩 된 클래스를 정의 하려고 했습니다 있지만 중첩 된 클래스는 기본 클래스, 하지 가장 포함 하는 클래스의 멤버입니다.  
  
 다음 샘플에서는 C2427 오류가 생성 됩니다.  
  
```  
// C2427.cpp  
// compile with: /c  
template <class T>   
struct S {  
   struct Inner;   
};   
  
struct Y : S<int> {};   
  
struct Y::Inner {};   // C2427  
  
// OK  
template<typename T>  
struct S<T>::Inner {};  
```