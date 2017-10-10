---
title: "컴파일러 오류 C2062 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2062
dev_langs:
- C++
helpviewer_keywords:
- C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 775923345052aba99b05f708c417b8bed267119b
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2062"></a>컴파일러 오류 C2062
예기치 않은 ' type' 형식  
  
 컴파일러는 형식 이름이 예기치 않은 합니다.  
  
 다음 샘플에서는 C2062 오류가 생성 됩니다.  
  
```  
// C2062.cpp  
// compile with: /c  
struct A {  : int l; };   // C2062  
struct B { private: int l; };   // OK  
```  
  
 C2062도 발생할 수 있습니다 컴파일러는 방식 때문에 생성자의 매개 변수 목록에 정의 되지 않은 형식을 처리 합니다. 컴파일러는 정의 되지 않은 (맞춤법이 틀린된) 형식 발생 하면 생성자는 식 및 c2062 가정 합니다. 를 해결 하려면만 생성자 매개 변수 목록에 정의 된 형식을 사용 합니다.
