---
title: "컴파일러 경고 C4693 | Microsoft Docs"
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
  - "C4693"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4693"
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 C4693
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': 봉인 추상 클래스는 인스턴스 멤버 'Test'를 포함할 수 없습니다.  
  
 형식이 [sealed](../../windows/sealed-cpp-component-extensions.md) 및 [abstract](../../windows/abstract-cpp-component-extensions.md)로 표시되어 있으면 정적 멤버만 사용할 수 있습니다.  
  
## 예제  
 다음 샘플에서는 C4693을 생성합니다.  
  
```  
// C4693.cpp // compile with: /clr /c public ref class Public_Ref_Class sealed abstract { public: void Test() {}   // C4693 static void Test2() {}   // OK };  
```