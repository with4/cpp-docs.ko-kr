---
title: "ConvertStringToBSTR | Microsoft Docs"
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
  - "ConvertStringToBSTR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ConvertStringToBSTR 함수"
ms.assetid: 071f9b3b-9643-4e06-a1e5-de96ed15bab2
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ConvertStringToBSTR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 **char \*** 값을 `BSTR`로 변환합니다.  
  
## 구문  
  
```  
  
      BSTR __stdcall ConvertStringToBSTR(  
   const char* pSrc  
)  
```  
  
#### 매개 변수  
 `pSrc`  
 **char \*** 변수입니다.  
  
## 예제  
  
```  
// ConvertStringToBSTR.cpp  
#include <comutil.h>  
#include <stdio.h>  
  
#pragma comment(lib, "comsuppw.lib")  
#pragma comment(lib, "kernel32.lib")  
  
int main() {  
   char* lpszText = "Test";  
   printf_s("char * text: %s\n", lpszText);  
  
   BSTR bstrText = _com_util::ConvertStringToBSTR(lpszText);  
   wprintf_s(L"BSTR text: %s\n", bstrText);  
  
   SysFreeString(bstrText);  
}  
```  
  
  **char \* 텍스트: 테스트**  
**BSTR 텍스트: 테스트**   
## Microsoft 전용 종료  
  
## 요구 사항  
 **Header:** comutil.h  
  
 **Lib:** comsuppw.lib 또는 comsuppwd.lib\(자세한 내용은 [\/Zc:wchar\_t\(wchar\_t를 네이티브 형식으로 인식\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 참조\)  
  
## 참고 항목  
 [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)