---
title: "컴파일러 오류 C3272 | Microsoft Docs"
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
  - "C3272"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3272"
ms.assetid: 7cdf254d-f207-4116-a1bf-7386f3b82a6f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3272
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol': 기호는 StructLayout\(LayoutKind::Explicit\)으로 정의된 typename 형식의 멤버이므로 FieldOffset이 필요합니다.  
  
 [StructLayout](frlrfSystemRuntimeInteropServicesStructLayoutAttributeClassTopic) `Explicit`가 적용된 경우 필드가 [FieldOffset](frlrfSystemRuntimeInteropServicesFieldOffsetAttributeClassTopic)으로 표시되어야 합니다.  
  
 다음 샘플에서는 C3272를 생성합니다.  
  
```  
// C3272_2.cpp // compile with: /clr /c using namespace System; using namespace System::Runtime::InteropServices; [StructLayout(LayoutKind::Explicit)] ref struct X { int data_;   // C3272 // try the following line instead // [FieldOffset(0)] int data_; };  
```  
  
 다음 샘플에서는 C3272를 생성합니다.  
  
```  
// C3272.cpp // compile with: /clr:oldSyntax /LD #using <mscorlib.dll> using namespace System; using namespace System::Runtime::InteropServices; [StructLayout(LayoutKind::Explicit)] __gc struct X { int data_;   // C3272 // try the following line instead // [FieldOffset(0)] int data_; };  
```