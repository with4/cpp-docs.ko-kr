---
title: "컴파일러 오류 C3210 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3210
dev_langs:
- C++
helpviewer_keywords:
- C3210
ms.assetid: c6e9d309-fabc-4e7d-b526-be20d9fe3f6a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b710aa15591a0e8a0a5613d5023ea7ba48d13d70
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3210"></a>컴파일러 오류 C3210
'type': 액세스 선언은 기본 클래스 멤버에만 적용할 수 있습니다  
  
 A [선언을 사용 하 여](../../cpp/using-declaration.md) 잘못 지정 되었습니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3210 오류가 발생 합니다.  
  
```  
// C3210.cpp  
// compile with: /c  
struct A {  
protected:  
   int i;  
};  
  
struct B {  
   using A::i;   // C3210  
};  
  
struct C : public A {  
   using A::i;   // OK  
};  
```