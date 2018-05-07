---
title: 컴파일러 오류 C2917 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2917
dev_langs:
- C++
helpviewer_keywords:
- C2917
ms.assetid: ec9da9ee-0f37-47b3-87dd-19ef5a14dc4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ecc5f8634505dc8b63cb4cbdbbb9aa31973e7475
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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