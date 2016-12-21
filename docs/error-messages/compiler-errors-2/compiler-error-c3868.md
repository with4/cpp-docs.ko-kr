---
title: "컴파일러 오류 C3868 | Microsoft Docs"
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
  - "C3868"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3868"
ms.assetid: f0e45c2a-2149-4885-a03b-0d230069f03a
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3868
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 제네릭 매개 변수 'parameter'에 대한 제약 조건이 선언에 대한 제약 조건과 다릅니다.  
  
 여러 선언의 제네릭 제약 조건은 동일해야 합니다.  자세한 내용은 [Generics](../../windows/generics-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3868 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3868.cpp  
// compile with: /clr /c  
interface struct I1;  
  
generic <typename T> ref struct MyStruct;  
generic <typename U> where U : I1 ref struct MyStruct;   // C3868  
  
// OK  
generic <typename T> ref struct MyStruct2;  
generic <typename U> ref struct MyStruct2;  
  
generic <typename T> where T : I1 ref struct MyStruct3;  
generic <typename U> where U : I1 ref struct MyStruct3;  
```