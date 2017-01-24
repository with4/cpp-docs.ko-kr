---
title: "컴파일러 오류 C2756 | Microsoft Docs"
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
  - "C2756"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2756"
ms.assetid: 42eb988d-4043-4dee-8fd4-596949f69a55
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2756
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'template type' : 부분 특수화에는 기본 템플릿 인수를 사용할 수 없습니다.  
  
 부분 특수화에 대한 템플릿에는 기본 인수가 포함될 수 없습니다.  
  
 다음 샘플에서는 C2756을 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2756.cpp  
template <class T>  
struct S {};  
  
template <class T=int>  
// try the following line instead  
// template <class T>  
struct S<T*> {};   // C2756  
```