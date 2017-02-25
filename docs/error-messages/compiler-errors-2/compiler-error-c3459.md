---
title: "컴파일러 오류 C3459 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3459"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3459"
ms.assetid: 3d290a20-d313-4c07-9bd8-c5c159cb169f
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 컴파일러 오류 C3459
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribute': 특성은 클래스 인덱서\(인덱싱된 기본 속성\)에만 사용할 수 있습니다.  
  
 클래스 인덱서 속성에 적용하기 위한 특성을 잘못 사용했습니다.  
  
 자세한 내용은 [방법: 인덱싱된 속성 사용](../../misc/how-to-use-indexed-properties.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3459를 생성합니다.  
  
```  
// C3459.cpp // compile with: /clr /c public ref class MyString { public: [System::Runtime::CompilerServices::IndexerName("Chars")]   // C3459 property int Prop; }; // OK public ref class MyString2 { array<int>^ MyArr; public: MyString2() { MyArr = gcnew array<int>(5); } [System::Runtime::CompilerServices::IndexerName("Chars")]   // OK property int default[int] { int get(int index) { return MyArr[index]; } void set(int index, int value) { MyArr[index] = value; } } };  
```