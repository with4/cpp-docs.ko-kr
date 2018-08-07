---
title: 컴파일러 오류 C2351 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2351
dev_langs:
- C++
helpviewer_keywords:
- C2351
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1660e5dfc4f17f7617c82eb3e633f345e2774495
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33222383"
---
# <a name="compiler-error-c2351"></a>컴파일러 오류 C2351
사용 되지 않는 c + + 생성자 초기화 구문입니다.  
  
 생성자는 새 스타일 초기화 목록에서 유일한 기본 클래스가 있는 경우에 각 직접 기본 클래스를 명시적으로 이름을 지정 해야 있습니다.  
  
 다음 샘플에서는 C2351 오류가 생성 됩니다.  
  
```  
// C2351.cpp  
// compile with: /c  
class B {  
public:   
   B() : () {}   // C2351  
   B() {}   // OK  
};  
```