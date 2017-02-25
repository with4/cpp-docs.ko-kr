---
title: "방법: 값 형식에 대한 참조를 네이티브 형식에 저장 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "값 형식에 대한 참조를 네이티브 형식에 저장"
  - "값 형식 참조를 네이티브 형식에 저장"
ms.assetid: 1eabf8be-7d4f-4339-9027-48d5c4244483
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 방법: 값 형식에 대한 참조를 네이티브 형식에 저장
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

값 형식에 대한 참조를 네이티브 형식에 저장하려면 boxed 형식에 `gcroot`를 사용합니다.  
  
## 예제  
  
```  
// reference_to_value_in_native.cpp  
// compile with: /clr  
#using <mscorlib.dll>  
#include <vcclr.h>   
  
using namespace System;   
  
public value struct V {  
   String ^str;  
};  
  
class Native {  
public:  
   gcroot< V^ > v_handle;  
};  
  
int main() {  
   Native native;  
   V v;  
   native.v_handle = v;  
   native.v_handle->str = "Hello";  
   Console::WriteLine("String in V: {0}", native.v_handle->str);  
}  
```  
  
  **String in V: Hello**   
## 참고 항목  
 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)