---
title: "컴파일러 오류 C2768 | Microsoft Docs"
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
  - "C2768"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2768"
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2768
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 명시적 템플릿 인수를 잘못 사용하였습니다.  
  
 함수 정의가 함수 템플릿의 명시적 특수화인지 아니면 새 함수에 사용하기 위한 것인지 여부를 컴파일러에서 확인할 수 없습니다.  
  
 이 오류는 Visual Studio .NET 2003의 향상된 컴파일러 규칙에 따라 Visual Studio .NET 2003에서 처음 발생합니다.  
  
 다음 샘플에서는 C2768 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2768.cpp  
template<typename T>  
void f(T) {}  
  
void f<int>(int) {}   // C2768  
  
// an explicit specialization  
template<>  
void f<int>(int) {}   
  
// global nontemplate function overload  
void f(int) {}  
```