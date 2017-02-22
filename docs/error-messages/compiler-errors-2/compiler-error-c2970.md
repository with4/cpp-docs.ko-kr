---
title: "컴파일러 오류 C2970 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2970"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2970"
ms.assetid: 21d90348-20d3-438c-b278-efdbfb93a7d2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2970
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 템플릿 매개 변수 'param' : 'arg' : 내부 링크가 있는 개체를 포함하는 식을 비형식 인수로 사용할 수 없습니다.  
  
 정적 변수의 주소 또는 이름을 템플릿 인수로 사용할 수 없습니다.  템플릿 클래스에 컴파일 타임에 계산할 수 있는 const 값이 필요합니다.  
  
 다음 샘플에서는 C2970 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2970.cpp  
// compile with: /c  
static int si;  
// could declare nonstatic to resolve all errors  
// int si;  
  
template <int i>   
class X {};  
  
template <int *pi>   
class Y {};  
  
X<si> anX;   // C2970 cannot use static variable in templates  
  
// this would also work  
const int i = 10;  
X<i> anX2;  
```