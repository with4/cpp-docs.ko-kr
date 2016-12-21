---
title: "ConvertBSTRToString | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "ConvertBSTRToString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ConvertBSTRToString 함수"
ms.assetid: ab6ce555-3d75-4e9c-9cb8-ada6d8ce43b1
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ConvertBSTRToString
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `BSTR` 값을 **char \***로 변환합니다.  
  
## 구문  
  
```  
  
      char* __stdcall ConvertBSTRToString(  
   BSTR pSrc  
);  
```  
  
#### 매개 변수  
 `pSrc`  
 BSTR 변수입니다.  
  
## 설명  
 `ConvertBSTRToString`은 삭제해야 하는 문자열을 할당합니다.  
  
## 예제  
  
```  
// ConvertBSTRToString.cpp  
#include <comutil.h>  
#include <stdio.h>  
  
#pragma comment(lib, "comsuppw.lib")  
  
int main() {  
   BSTR bstrText = ::SysAllocString(L"Test");  
   wprintf_s(L"BSTR text: %s\n", bstrText);  
  
   char* lpszText2 = _com_util::ConvertBSTRToString(bstrText);  
   printf_s("char * text: %s\n", lpszText2);  
  
   SysFreeString(bstrText);  
   delete[] lpszText2;  
}  
```  
  
  **BSTR 텍스트: 테스트**  
**char \* 텍스트: 테스트**   
## Microsoft 전용 종료  
  
## 요구 사항  
 **헤더:** comutil.h.  
  
 **Lib:** comsuppw.lib 또는 comsuppwd.lib\(자세한 내용은 [\/Zc:wchar\_t\(wchar\_t를 네이티브 형식으로 인식\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 참조\)  
  
## 참고 항목  
 [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)