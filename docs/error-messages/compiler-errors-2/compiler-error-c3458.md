---
title: "컴파일러 오류 C3458 | Microsoft Docs"
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
  - "C3458"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3458"
ms.assetid: 940202fd-8dcc-4042-9c96-3f9e9127d2f1
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3458
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribute1': 'attribute2' 특성이 'construct'에 대해 이미 지정되어 있습니다.  
  
 함께 사용할 수 없는 두 특성이 동일한 구문에 대해 지정되었습니다.  
  
## 예제  
 다음 샘플에서는 C3458을 생성합니다.  
  
```  
// C3458.cpp // compile with: /clr /c [System::Reflection::DefaultMember("Chars")] public ref class MyString { public: [System::Runtime::CompilerServices::IndexerName("Chars")]   // C3458 property char default[int] { char get(int index); void set(int index, char c); } };  
```