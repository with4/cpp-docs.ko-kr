---
title: "C++ 마샬링 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "marshaling"
  - "marshalling"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ 지원 라이브러리, 마샬링"
  - "마샬링, 마샬링 정보"
  - "Visual C++, 마샬링"
ms.assetid: 997dd4bc-5f98-408f-b890-f35de9ce3bb8
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ 마샬링 개요
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

혼합된 모드에서, 때때로 네이티브 및 관리 되는 형식 간에 데이터를 마샬링 해야합니다.  [!INCLUDE[vs_orcas_long](../atl/reference/includes/vs_orcas_long_md.md)] 은 간단한 방법으로 데이터를 변환하고 마샬링 하는 데 도움을 줄 마샬링 라이브러리를 도입합니다.  
  
 [marshal\_context 클래스](../dotnet/marshal-context-class.md)의 여부와 관계없이 마샬링 라이브러리를 사용할 수 있습니다.  일부 변환은 컨텍스트가 필요 합니다.  [marshal\_as](../dotnet/marshal-as.md) 함수를 사용하여 다른 변환을 구현할 수 있습니다.  다음 표는 컨텍스트 필요 여부와 어떤 마샬 파일을 포함해야 하는 지, 그리고 현재 지원되는 변환을 나타냅니다.  
  
|형식으로부터|\<대상 형식\>|Marshal 메서드|파일 포함하기|  
|------------|---------------|-----------------|-------------|  
|System::String^|const char \*|marshal\_context|marshal.h|  
|const char \*|System::String^|marshal\_as|marshal.h|  
|char\*|System::String^|marshal\_as|marshal.h|  
|System::String^|const wchar\_t\*|marshal\_context|marshal.h|  
|const wchar\_t \*|System::String^|marshal\_as|marshal.h|  
|wchar\_t\*|System::String^|marshal\_as|marshal.h|  
|System::IntPtr|HANDLE|marshal\_as|windows.h를 마샬링하다|  
|HANDLE|System::IntPtr|marshal\_as|windows.h를 마샬링하다|  
|System::String^|BSTR|marshal\_context|windows.h를 마샬링하다|  
|BSTR|System::String^|marshal\_as|marshal.h|  
|System::String^|bstr\_t|marshal\_as|windows.h를 마샬링하다|  
|bstr\_t|System::String^|marshal\_as|windows.h를 마샬링하다|  
|System::String^|std::string|marshal\_as|cppstd.h를 마샬링하다|  
|std::string|System::String^|marshal\_as|cppstd.h를 마샬링하다|  
|System::String^|std::wstring|marshal\_as|cppstd.h를 마샬링하다|  
|std::wstring|System::String^|marshal\_as|cppstd.h를 마샬링하다|  
|System::String^|CStringT\<문자\>|marshal\_as|atl.h를 마샬링하다|  
|CStringT\<문자\>|System::String^|marshal\_as|atl.h를 마샬링하다|  
|System::String^|CStringT\<wchar\_t\>|marshal\_as|atl.h를 마샬링하다|  
|CStringT\<wchar\_t\>|System::String^|marshal\_as|atl.h를 마샬링하다|  
|System::String^|CComBSTR|marshal\_as|atl.h를 마샬링하다|  
|CComBSTR|System::String^|marshal\_as|atl.h를 마샬링하다|  
  
 마샬링은 관리되는 것에서 부터 네이티브 데이터 형식까지 마샬링할 때 오직 컨텍스트만 요구하고 변환 하고 있는 네이티브 형식은 자동 소멸을 위한 소멸자를 가질 필요가 없습니다.  마샬링 컨텍스트는 소멸자에서 할당된 원시 데이터 형식을 삭제합니다.  따라서, 컨텍스트가 삭제 될 때까지 컨텍스트가 필요한 변환은 유효 하지 않습니다.  마샬링된 값을 저장 하려면 변수에 직접 값 복사 해야 합니다.  
  
> [!NOTE]
>  `NULL`s 이 문자열에 내장되어 있다면, 문자열을 마샬링 한 결과를 보장할 수 없습니다.  포함된 `NULL`s은 문자열을 자르게 하거나 또는 그대로 유지하게 할 수 있습니다.  
  
 마샬링 라이브러리 헤더는 msclr 하위 디렉터리에 있습니다.  이 예제에서는 포함 헤더 선언에 msclr 디렉터리를 포함하는 방법을 보여 줍니다.  
  
 `#include "msclr\marshal_cppstd.h"`  
  
 마샬링 라이브러리는 마샬링 형식을 추가할 수 있도록 확장이 가능 합니다.  마샬링 라이브러리를 확장하는 것에 대한 자세한 내용은 [방법: 마샬링 라이브러리 확장](../dotnet/how-to-extend-the-marshaling-library.md)를 참조하십시오.  
  
 이전 버전에서, [플랫폼 호출](../Topic/Consuming%20Unmanaged%20DLL%20Functions.md)을 사용하여 데이터를 마샬링 할 수 있습니다.  `PInvoke`에 대한 자세한 내용은 [관리 코드에서 네이티브 함수 호출](../dotnet/calling-native-functions-from-managed-code.md)을 참조하십시오.  
  
## 참고 항목  
 [C\+\+ 지원 라이브러리](../dotnet/cpp-support-library.md)   
 [방법: 마샬링 라이브러리 확장](../dotnet/how-to-extend-the-marshaling-library.md)