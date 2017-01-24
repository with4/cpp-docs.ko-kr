---
title: "컴파일러 오류 C3200 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3200"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3200"
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3200
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'template' : 템플릿 매개 변수 'parameter'의 템플릿 인수가 잘못되었습니다. 클래스 템플릿이 필요합니다.  
  
 클래스 템플릿에 잘못된 인수를 전달했습니다.  클래스 템플릿은 템플릿을 매개 변수로 간주합니다.  다음 예제에서 `Y<int, int> aY`를 호출하면 C3200이 발생합니다.  첫째 매개 변수는 템플릿이어야 합니다\(예: `Y<X, int> aY`\).  
  
```  
// C3200.cpp  
template<typename T>  
class X  
{  
};  
  
template<template<typename U> class T1, typename T2>  
class Y  
{  
};  
  
int main()  
{  
   Y<int, int> y;   // C3200  
}  
```