---
title: "컴파일러 오류 C3222 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3222
dev_langs:
- C++
helpviewer_keywords:
- C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: edc882f340e92defeaa2db92d868680f7791e7b9
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3222"></a>컴파일러 오류 C3222
'parameter': 제네릭 함수 또는 관리되는 또는 WinRT 형식의 멤버 함수에 대한 기본 인수를 선언할 수 없습니다.  
  
기본 인수를 사용하는 메서드 매개 변수를 선언할 수 없습니다. 메서드의 오버로드된 형식은 이 문제를 해결하는 한 가지 방법입니다. 즉, 매개 변수 없이 동일한 이름을 사용하는 메서드를 정의한 다음 메서드 본문에서 변수를 초기화합니다.  
  
다음 샘플에서는 C3222를 생성합니다.  
  
```  
// C3222_2.cpp  
// compile with: /clr  
public ref class G {  
   void f( int n = 0 );   // C3222  
};  
```  

