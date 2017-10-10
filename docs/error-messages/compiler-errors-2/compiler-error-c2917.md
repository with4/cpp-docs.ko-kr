---
title: "컴파일러 오류 C2917 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2917
dev_langs:
- C++
helpviewer_keywords:
- C2917
ms.assetid: ec9da9ee-0f37-47b3-87dd-19ef5a14dc4c
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b66aee3abc57f7505f829fcedffdf2ffd927d839
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2917"></a>컴파일러 오류 C2917
'name': 템플릿-매개 변수가 잘못되었습니다.  
  
 템플릿 매개 변수 목록에 템플릿 매개 변수가 아닌 식별자가 포함되어 있습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2917을 생성합니다.  
  
```  
// C2917.cpp  
// compile with: /c  
template<class T> class Vector {  
   void sort();  
};  
  
template<class T*> void Vector<T>::sort() {}   // C2917  
// try the following line instead  
// template<class T> void Vector<T>::sort() {}  
```
