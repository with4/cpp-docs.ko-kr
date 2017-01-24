---
title: "컴파일러 오류 C3213 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3213"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3213"
ms.assetid: 1f079e36-b3e9-40f8-8e95-08eeba3adc82
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3213
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 클래스 'base\_type'이 'derived\_type'보다 액세스하기 어렵습니다.  
  
 어셈블리에서 볼 수 있는 형식은 공개적으로 볼 수 있는 기본 클래스를 사용해야 합니다.  
  
 다음 샘플에서는 C3213을 생성합니다.  
  
```  
// C3213.cpp // compile with: /clr private ref struct privateG { public: int i; }; public ref struct publicG { public: int i; }; public ref struct V : public privateG {   // C3213 public: int j; }; public ref struct W: public publicG {   // OK public: int j; };  
```