---
title: 컴파일러 오류 C2943 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2943
dev_langs:
- C++
helpviewer_keywords:
- C2943
ms.assetid: ede6565e-d892-44c0-8eee-c69545f3be2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6009428a151ee9959766db6213d2447eaf836c2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2943"></a>컴파일러 오류 C2943
'class': type-class-id가 템플릿의 형식 인수로 재정의되었습니다.  
  
 제네릭 또는 템플릿 클래스를 기호 대신 제네릭 또는 템플릿 형식 인수로 사용할 수 없습니다.  
  
 다음 샘플에서는 C2943을 생성합니다.  
  
```  
// C2943.cpp  
// compile with: /c  
template<class T>  
class List {};  
  
template<class List<int> > class MyList;   // C2943  
template<class T >  class MyList;  
```