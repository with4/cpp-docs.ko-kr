---
title: "marshal_as | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "marshal_as"
  - "msclr.interop.marshal_as"
  - "msclr::interop::marshal_as"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_as 템플릿[C++]"
ms.assetid: 2ed717da-2b11-41e5-981d-47d251771989
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# marshal_as
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 메서드는 네이티브 및 관리 환경 사이 데이터를 변환합니다.  
  
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
 이 메서드는 네이티브 및 관리 되는 형식 간에 데이터를 변환 하는 간단한 방법입니다.  참조 데이터 형식 사용을 결정 하려면 [C\+\+ 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md)을 확인하십시오.  일부 데이터 변환은 컨텍스트가 필요합니다.  [marshal\_context 클래스](../dotnet/marshal-context-class.md)을 사용하여 이러한 데이터 형식을 변환할 수 있습니다.  
  
 지원하지 않는 데이터 형식 쌍을 마샬링하는 경우, 컴파일 타임에  `marshal_as` 은 [c 4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) 오류가 발생니다.  이 오류에 대한 자세한 내용이 함께 제공된 메시지를 읽으십시오.   `C4996` 오류는 사용 지양된 함수보다 더 많이 생성될 수 있습니다.  하나의 예로는 지원되지 않는 한 쌍의 데이터 형식을 마샬링하려고 하는 것입니다.  
  
 마샬링 라이브러리는 여러 개의 헤더 파일 구성됩니다.  모든 변환 파일은 하나만 필요하지만, 다른 변환해야 할 경우 추가 파일을 포함할 수 있습니다.  어떤 파일을 연결된 변환을 보려면,  `Marshaling Overview` 의 표를 확인하십시오.  변환하려는 것에 관계 없이 네임 스페이스 요구는 항상 유효 합니다.  
  
## 예제  
 이 예제에서는  `const char*` 부터  `System::String`  변수 형식을 마샬링합니다.  
  
```  
// marshal_as_test.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   const char* message = "Test String to Marshal";  
   String^ result;  
   result = marshal_as<String^>( message );  
   return 0;  
}  
```  
  
## 요구 사항  
 **헤더 파일:**\<msclr\\marshal.h\>, \<msclr\\marshal\_windows.h\>, \<msclr\\marshal\_cppstd.h\>, 또는 \<msclr\\marshal\_atl.h \>  
  
 **네임 스페이스:** msclr::interop  
  
## 참고 항목  
 [C\+\+ 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_context 클래스](../dotnet/marshal-context-class.md)