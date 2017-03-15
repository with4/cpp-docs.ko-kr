---
title: "marshal_context::marshal_as | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "marshal_context::marshal_as"
  - "marshal_context.marshal_as"
  - "msclr.interop.marshal_context.marshal_as"
  - "msclr::interop::marshal_context::marshal_as"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_context 클래스[C++], 작업"
ms.assetid: 24a1afee-51c0-497c-948c-f77fe43635c8
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# marshal_context::marshal_as
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Performs the marshaling on a specific data object to convert it between a managed and a native data type.  
  
## 구문  
  
```  
To_Type marshal_as<To_Type>(  
   From_Type input   
);  
```  
  
#### 매개 변수  
 \[in\] `input`  
 `To_Type`  값으로 마샬링하는 변수입니다.  
  
## 반환 값  
 `input` 값이 변환 된  `To_Type` 형식의 변수입니다.  
  
## 설명  
 This function performs the marshaling on a specific data object.  Use this function only with the conversions indicated by the table in [C\+\+ 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md).  
  
 지원하지 않는 데이터 형식 쌍을 마샬링하는 경우, 컴파일 타임에  `marshal_as` 은 [c 4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) 오류가 발생니다.  이 오류에 대한 자세한 내용이 함께 제공된 메시지를 읽으십시오.   `C4996` 오류는 사용 지양된 함수보다 더 많이 생성될 수 있습니다.  Two conditions that will generate this error are trying to marshal a pair of data types that are not supported and trying to use `marshal_as` for a conversion that requires a context.  
  
 마샬링 라이브러리는 여러 개의 헤더 파일 구성됩니다.  모든 변환 파일은 하나만 필요하지만, 다른 변환해야 할 경우 추가 파일을 포함할 수 있습니다.  The table in `Marshaling Overview in C++` indicates which marshaling file should be included for each conversion.  
  
## 예제  
 This example creates a context for marshaling from a `System::String` to a `const char *` variable type.  The converted data will not be valid after the line that deletes the context.  
  
```  
// marshal_context_test.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   marshal_context^ context = gcnew marshal_context();  
   String^ message = gcnew String("Test String to Marshal");  
   const char* result;  
   result = context->marshal_as<const char*>( message );  
   delete context;  
   return 0;  
}  
```  
  
## 요구 사항  
 **헤더 파일:**\<msclr\\marshal.h\>, \<msclr\\marshal\_windows.h\>, \<msclr\\marshal\_cppstd.h\>, 또는 \<msclr\\marshal\_atl.h \>  
  
 **네임 스페이스:** msclr::interop  
  
## 참고 항목  
 [C\+\+ 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_as](../dotnet/marshal-as.md)   
 [marshal\_context 클래스](../dotnet/marshal-context-class.md)