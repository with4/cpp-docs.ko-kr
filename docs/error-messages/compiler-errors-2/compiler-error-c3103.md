---
title: "컴파일러 오류 C3103 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3103"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3103"
ms.assetid: 7984bd3e-d51d-43e4-b6f4-08c1e9fb9704
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3103
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'argument': 명명된 인수가 반복되었습니다.  
  
 특성에서는 명명된 인수를 반복할 수 없습니다.  
  
 자세한 내용은 [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3103 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3103.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::All)]  
public ref class Attr : public Attribute {  
public:  
   int m_t;  
};  
  
[Attr(m_t = 10, m_t = 1)]   // C3103  
// try the following line instead  
// [Attr(m_t = 10)]  
ref class A {};  
```