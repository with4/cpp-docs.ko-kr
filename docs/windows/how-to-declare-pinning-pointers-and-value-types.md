---
title: "How to: Declare Pinning Pointers and Value Types | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value types, declaring"
  - "pinning pointers"
ms.assetid: 57c5ec8a-f85a-48c4-ba8b-a81268bcede0
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Declare Pinning Pointers and Value Types
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

값 형식은 절대적 형식이 될 수 있습니다.  형식 개체에 대한 고정 포인터를 선언하고 boxed 값 형식에 **pin\_ptr** 을 사용할 수 있습니다.  
  
## 예제  
  
### 코드  
  
```  
// pin_ptr_value.cpp  
// compile with: /clr  
value struct V {  
   int i;  
};  
  
int main() {  
   V ^ v = gcnew V;   // imnplicit boxing  
   v->i=8;  
   System::Console::WriteLine(v->i);  
   pin_ptr<V> mv = &*v;  
   mv->i = 7;  
   System::Console::WriteLine(v->i);  
   System::Console::WriteLine(mv->i);  
}  
```  
  
### Output  
  
```  
8  
7  
7  
```  
  
## 참고 항목  
 [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md)