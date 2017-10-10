---
title: "컴파일러 오류 C2755 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2755
dev_langs:
- C++
helpviewer_keywords:
- C2755
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 56889ff193d057104c25b31bea8029e9426a9bbc
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2755"></a>컴파일러 오류 C2755
'param': 부분 특수화의 비형식 매개 변수는 단순 식별자 여야 합니다.  
  
 비형식 매개 변수는 단순 식별자를 컴파일러에서 컴파일 타임에 하나의 식별자 또는 상수 값에 확인할 수 있어야 합니다.  
  
 다음 샘플에서는 C2755 오류가 생성 됩니다.  
  
```  
// C2755.cpp  
template<int I, int J>  
struct A {};  
  
template<int I>   
struct A<I,I*5> {};   // C2755  
// try the following line instead  
// struct A<I,5> {};  
```
