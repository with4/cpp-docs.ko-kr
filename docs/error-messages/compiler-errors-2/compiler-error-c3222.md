---
title: "컴파일러 오류 C3222 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: bd1058f4e33bc70c9021bfb1ceff78af58d09552
ms.lasthandoff: 02/24/2017

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

