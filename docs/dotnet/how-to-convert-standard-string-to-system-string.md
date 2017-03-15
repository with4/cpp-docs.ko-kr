---
title: "방법: 표준 문자열을 System::String으로 변환 | Microsoft Docs"
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
  - "표준 C++ 라이브러리, 문자열을 System::String으로 변환"
  - "문자열 변환[C++], 표준 C++ 라이브러리 문자열"
  - "문자열[C++], 변환"
ms.assetid: 1fde79a0-9d0b-44e5-981b-e8f2676c199d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 방법: 표준 문자열을 System::String으로 변환
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 표준 C\+\+ 라이브러리 문자열\([\<string\>](../standard-library/string.md)\)을 <xref:System.String>으로 변환하는 방법을 보여 줍니다.  
  
## 예제  
  
```  
// convert_standard_string_to_system_string.cpp  
// compile with: /clr  
#include <string>  
#include <iostream>  
using namespace System;  
using namespace std;  
  
int main() {  
   string str = "test";  
   cout << str << endl;  
   String^ str2 = gcnew String(str.c_str());  
   Console::WriteLine(str2);  
  
   // alternatively  
   String^ str3 = gcnew String(str.c_str());  
   Console::WriteLine(str3);  
}  
```  
  
  **테스트**  
**테스트**  
**테스트**   
## 참고 항목  
 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)