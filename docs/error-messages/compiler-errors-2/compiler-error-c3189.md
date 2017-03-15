---
title: "컴파일러 오류 C3189 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3189"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3189"
ms.assetid: b254de79-931e-4a59-a9f4-1c690d90ca5e
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3189
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'typeid\<type abstract declarator\>': 이 구문은 더 이상 지원되지 않습니다. 대신 ::typeid를 사용하십시오.  
  
 이제는 사용되지 않는 형식의 [typeid](../../windows/typeid-cpp-component-extensions.md)를 사용했습니다. 새 구문을 사용하십시오.  
  
 다음 샘플에서는 C3189 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3189.cpp  
// compile with: /clr  
int main() {  
   System::Type^ t  = typeid<System::Object>;   // C3189  
   System::Type^ t2  = System::Object::typeid;   // OK  
}  
```