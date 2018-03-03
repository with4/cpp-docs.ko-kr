---
title: "컴파일러 오류 C2698 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2698
dev_langs:
- C++
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b2bc9be3cfa38b4789feb35ae57015b78ad079c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2698"></a>컴파일러 오류 C2698
using 선언은 ' 선언 1'의 기존 using 선언과 공존할 수 없습니다 ' 2' 선언  
  
 있으면는 [선언을 사용 하 여](../../cpp/using-declaration.md) 사용 하 여 모든 데이터 멤버에 대 한 선언이 동일한 이름을 사용 하는 동일한 범위에서 허용 되지 않습니다만 함수를 오버 로드할 수 있습니다.  
  
 다음 샘플에서는 C2698 오류가 생성 됩니다.  
  
```  
// C2698.cpp  
struct A {  
   int x;  
};  
  
struct B {  
   int x;  
};  
  
struct C : A, B {  
   using A::x;  
   using B::x;   // C2698  
}  
```