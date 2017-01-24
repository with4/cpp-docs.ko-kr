---
title: "_set_com_error_handler | Microsoft Docs"
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
  - "_set_com_error_handler 함수"
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _set_com_error_handler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 COM 오류 처리에 사용되는 기본 함수를 대체합니다.  
  
## 구문  
  
```  
void __stdcall _set_com_error_handler(  
   void (__stdcall *pHandler)(  
      HRESULT hr,   
      IErrorInfo* perrinfo  
   )  
);  
```  
  
#### 매개 변수  
 `pHandler`  
 대체 함수에 대한 포인터입니다.  
  
 `hr`  
 `HRESULT` 정보입니다.  
  
 `perrinfo`  
 `IErrorInfo` 개체  
  
## 설명  
 기본적으로 [\_com\_raise\_error](../cpp/com-raise-error.md)는 모든 COM 오류를 처리합니다.  `_set_com_error_handler`를 사용하여 이 동작을 변경하여 사용자 고유의 오류 처리 함수를 호출할 수 있습니다.  
  
 대체 함수에는 `_com_raise_error`의 시그니처에 해당하는 시그니처가 있어야 합니다.  
  
## 예제  
  
```  
// _set_com_error_handler.cpp  
// compile with /EHsc  
#include <stdio.h>  
#include <comdef.h>  
#include <comutil.h>  
  
// Importing ado dll to attempt to establish an ado connection.  
// Not related to _set_com_error_handler   
#import "C:\Program Files\Common Files\System\ado\msado15.dll" no_namespace rename("EOF", "adoEOF")  
  
void __stdcall _My_com_raise_error(HRESULT hr, IErrorInfo* perrinfo)  
{  
   throw "Unable to establish the connection!";  
}  
  
int main()  
{  
   _set_com_error_handler(_My_com_raise_error);  
   _bstr_t bstrEmpty(L"");  
   _ConnectionPtr Connection = NULL;  
   try  
   {  
      Connection.CreateInstance(__uuidof(Connection));  
      Connection->Open(bstrEmpty, bstrEmpty, bstrEmpty, 0);   
   }  
   catch(char* errorMessage)  
   {  
      printf("Exception raised: %s\n", errorMessage);  
   }  
  
   return 0;  
}  
```  
  
  **Exception raised: Unable to establish the connection\!**   
## 요구 사항  
 **헤더:** comdef.h  
  
 **Lib:** "wchar\_t is Native Type" 컴파일러 옵션이 설정되어 있는 경우 comsuppw.lib 또는 comsuppwd.lib를 사용합니다.  "wchar\_t is Native Type"이 해제되어 있는 경우 comsupp.lib를 사용합니다.  자세한 내용은 [\/Zc:wchar\_t\(wchar\_t를 네이티브 형식으로 인식\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)을 참조하십시오.  
  
## 참고 항목  
 [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)