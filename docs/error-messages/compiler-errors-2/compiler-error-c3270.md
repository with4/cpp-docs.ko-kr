---
title: "컴파일러 오류 C3270 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3270"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3270"
ms.assetid: 70e6e76b-7415-48f5-a61e-2ed50caf08e4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3270
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'field': FieldOffset 특성은 필요한 StructLayout\(Explicit\) 컨텍스트에서만 사용할 수 있습니다.  
  
 필드가 [StructLayout](frlrfSystemRuntimeInteropServicesStructLayoutAttributeClassTopic) Explicit가 적용된 경우에만 허용되는 [FieldOffset](frlrfSystemRuntimeInteropServicesFieldOffsetAttributeClassTopic)으로 표시되었습니다.  
  
 다음 샘플에서는 C3270을 생성합니다.  
  
```  
// C3270_2.cpp // compile with: /clr /c using namespace System::Runtime::InteropServices; [ StructLayout(LayoutKind::Sequential) ] // try the following line instead // [ StructLayout(LayoutKind::Explicit) ] public value struct MYUNION { [FieldOffset(0)] int a;   // C3270 // ... };  
```  
  
 다음 샘플에서는 C3270을 생성합니다.  
  
```  
// C3270.cpp // compile with: /clr:oldSyntax /LD #using <mscorlib.dll> using namespace System::Runtime::InteropServices; [ StructLayout(LayoutKind::Sequential) ] // try the following line instead // [ StructLayout(LayoutKind::Explicit) ] public __value struct MYUNION { [FieldOffset(0)] int a;   // C3270 // ... };  
```