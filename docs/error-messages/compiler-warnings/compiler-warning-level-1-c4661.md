---
title: 컴파일러 경고 (수준 1) C4661 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4661
dev_langs:
- C++
helpviewer_keywords:
- C4661
ms.assetid: 603bb8b7-356d-4eef-924b-64d769bac5bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce88913a29dd9ec3f9d5d2e78c3e52ad3ead54fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33280951"
---
# <a name="compiler-warning-level-1-c4661"></a>컴파일러 경고(수준 1) C4661
'identifier': 명시적 템플릿 인스턴스화 요청에 대해 제공 된 적합 한 정의가 없습니다  
  
 템플릿 클래스의 멤버 정의 되지 않았습니다.  
  
## <a name="example"></a>예제  
  
```  
// C4661.cpp  
// compile with: /W1 /LD  
template<class T> class MyClass {  
public:  
   void i();   // declaration but not definition  
};  
template MyClass< int >;  // C4661  
```