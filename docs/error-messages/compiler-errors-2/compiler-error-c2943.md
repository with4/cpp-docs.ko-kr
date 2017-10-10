---
title: "컴파일러 오류 C2943 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2943
dev_langs:
- C++
helpviewer_keywords:
- C2943
ms.assetid: ede6565e-d892-44c0-8eee-c69545f3be2e
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1bbd2a3310bb3f5cd18c241f9923d051acde58eb
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

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
