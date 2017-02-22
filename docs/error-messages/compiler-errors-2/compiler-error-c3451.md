---
title: "컴파일러 오류 C3451 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3451"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3451"
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# 컴파일러 오류 C3451
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribute': 'type'에 관리되지 않는 특성을 적용할 수 없습니다.  
  
 CLR 형식에 C\+\+ 특성을 적용할 수 없습니다.  자세한 내용은 [C\+\+ Attributes Reference](../../windows/cpp-attributes-reference.md)를 참조하십시오.  
  
 자세한 내용은 [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)을 참조하십시오.  
  
 이 오류는 Visual C\+\+ 2005에 대해 적용되었으며, [uuid](../../windows/uuid-cpp-attributes.md) 특성이 CLR 프로그래밍을 사용한 사용자 정의 특성에서 더 이상 허용되지 않는다는 컴파일러 규칙의 결과로 발생할 수 있습니다.  대신 <xref:System.Runtime.InteropServices.GuidAttribute>를 사용하십시오.  
  
## 예제  
 다음 샘플에서는 C3451 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3451.cpp  
// compile with: /clr /c  
using namespace System;  
[ attribute(AttributeTargets::All) ]  
public ref struct MyAttr {};  
  
[ MyAttr, helpstring("test") ]   // C3451  
// try the following line instead  
// [ MyAttr ]  
public ref struct ABC {};  
```