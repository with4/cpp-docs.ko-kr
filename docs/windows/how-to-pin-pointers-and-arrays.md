---
title: "How to: Pin Pointers and Arrays | Microsoft Docs"
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
  - "pointers, pinning"
  - "arrays [C++], pinning"
ms.assetid: ee783260-e676-46b8-a38e-11a06f1d57b0
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Pin Pointers and Arrays
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

관리되는 개체에 정의 된 하위 개체를 고정하면 전체 개체를 고정하는 효과가 있습니다.  예를 들어, 모든 배열 요소가 고정 되어 있는 경우 다음 전체 배열도 고정됩니다.  고정 된 배열을 선언하는 언어에 더이상 확장이 없습니다.  핀 배열, 요소 형식 및 해당 요소 중 하나는 핀 고정 포인터를 선언합니다.  
  
## 예제  
  
### 코드  
  
```  
// pin_ptr_array.cpp  
// compile with: /clr  
#include <stdio.h>  
using namespace System;  
  
int main() {  
   array<Byte>^ arr = gcnew array<Byte>(4);  
   arr[0] = 'C';  
   arr[1] = '+';  
   arr[2] = '+';  
   arr[3] = '\0';  
   pin_ptr<Byte> p = &arr[1];   // entire array is now pinned  
   unsigned char * cp = p;  
  
   printf_s("%s\n", cp); // bytes pointed at by cp  
                         // will not move during call  
}  
```  
  
### Output  
  
```  
++  
```  
  
## 참고 항목  
 [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md)