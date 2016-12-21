---
title: "방법: System::String을 wchar_t* 또는 char*로 변환 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char 데이터 형식, System::String 변환"
  - "PtrToStringChars 메서드"
  - "System::String"
  - "System::String, char 또는 wchar_t로 변환"
  - "wchart 형식, System::String 변환"
ms.assetid: 385da01b-5649-4543-8076-e3e251243ff0
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: System::String을 wchar_t* 또는 char*로 변환
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vcclr.h에서 `PtrToStringChars`를 사용하여 <xref:System.String>을 네이티브 `wchar_t *` 또는 `char *`로 변환할 수 있습니다.  이렇게 하면 항상 와이드 유니코드 문자열 포인터가 반환됩니다. CLR 문자열은 내부적으로 유니코드이기 때문입니다.  그런 다음 아래 예제에서와 같이 와이드 문자열을 변환할 수 있습니다.  
  
## 예제  
  
```  
// convert_string_to_wchar.cpp  
// compile with: /clr  
#include < stdio.h >  
#include < stdlib.h >  
#include < vcclr.h >  
  
using namespace System;  
  
int main() {  
   String ^str = "Hello";  
  
   // Pin memory so GC can't move it while native function is called  
   pin_ptr<const wchar_t> wch = PtrToStringChars(str);  
   printf_s("%S\n", wch);  
  
   // Conversion to char* :  
   // Can just convert wchar_t* to char* using one of the   
   // conversion functions such as:   
   // WideCharToMultiByte()  
   // wcstombs_s()  
   // ... etc  
   size_t convertedChars = 0;  
   size_t  sizeInBytes = ((str->Length + 1) * 2);  
   errno_t err = 0;  
   char    *ch = (char *)malloc(sizeInBytes);  
  
   err = wcstombs_s(&convertedChars,   
                    ch, sizeInBytes,  
                    wch, sizeInBytes);  
   if (err != 0)  
      printf_s("wcstombs_s  failed!\n");  
  
    printf_s("%s\n", ch);  
}  
```  
  
  **Hello**  
**Hello**   
## 참고 항목  
 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)