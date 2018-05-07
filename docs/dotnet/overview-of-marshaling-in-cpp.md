---
title: C + + 마샬링 개요 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- marshaling
- marshalling
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, marshaling
- C++ Support Library, marshaling
- marshaling, about marshaling
ms.assetid: 997dd4bc-5f98-408f-b890-f35de9ce3bb8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1f950c8efbdd75e16096d158075e92594fb6b2d1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="overview-of-marshaling-in-c"></a>C++ 마샬링 개요
혼합된 모드의 경우에 따라 마샬링해야 네이티브 및 관리 되는 형식 간의 데이터. [!INCLUDE[vs_orcas_long](../atl/reference/includes/vs_orcas_long_md.md)] 마샬링 라이브러리를 도입 마샬링해야 하 고 간단한 방법으로 데이터를 변환 합니다.  
  
 여부에 관계 없이 마샬링 라이브러리를 사용할 수는 [marshal_context 클래스](../dotnet/marshal-context-class.md)합니다. 변환 중 일부는 컨텍스트가 필요합니다. 다른 변환을 사용 하 여 구현할 수 있습니다는 [marshal_as](../dotnet/marshal-as.md) 함수입니다. 다음 표에 지원 되는 현재 변환이는 컨텍스트가 필요 여부와 어떤 마샬링 파일 포함 해야 합니다.  
  
|형식에서|입력|마샬링 메서드|포함 파일|  
|---------------|-------------|--------------------|------------------|  
|System:: string ^|const char *|marshal_context|marshal.h|  
|const char *|System:: string ^|marshal_as|marshal.h|  
|char *|System:: string ^|marshal_as|marshal.h|  
|System:: string ^|const wchar_t*|marshal_context|marshal.h|  
|const wchar_t *|System:: string ^|marshal_as|marshal.h|  
|wchar_t *|System:: string ^|marshal_as|marshal.h|  
|System::IntPtr|HANDLE|marshal_as|marshal_windows.h|  
|HANDLE|System::IntPtr|marshal_as|marshal_windows.h|  
|System:: string ^|BSTR|marshal_context|marshal_windows.h|  
|BSTR|System:: string ^|marshal_as|marshal.h|  
|System:: string ^|bstr_t|marshal_as|marshal_windows.h|  
|bstr_t|System:: string ^|marshal_as|marshal_windows.h|  
|System:: string ^|std:: string|marshal_as|marshal_cppstd.h|  
|std:: string|System:: string ^|marshal_as|marshal_cppstd.h|  
|System:: string ^|std:: wstring|marshal_as|marshal_cppstd.h|  
|std:: wstring|System:: string ^|marshal_as|marshal_cppstd.h|  
|System:: string ^|CStringT\<char >|marshal_as|marshal_atl.h|  
|CStringT\<char >|System:: string ^|marshal_as|marshal_atl.h|  
|System:: string ^|CStringT < wchar_t >|marshal_as|marshal_atl.h|  
|CStringT < wchar_t >|System:: string ^|marshal_as|marshal_atl.h|  
|System:: string ^|CComBSTR|marshal_as|marshal_atl.h|  
|CComBSTR|System:: string ^|marshal_as|marshal_atl.h|  
  
 마샬링에 형식을 네이티브로 관리 되는 데이터에서 마샬링하 네이티브 형식으로 변환 하는 정리 자동에 대 한 소멸자가 없는 경우에는 컨텍스트가 필요 합니다. 마샬링 컨텍스트는 할당 된 원시 데이터 형식을 해당 소멸자에서 소멸 시킵니다. 따라서 컨텍스트 삭제 될 때까지 컨텍스트 해야 하는 변환은 유효한 됩니다. 마샬링된 모든 값을 저장 하려면 고유한 변수를 값을 복사 해야 합니다.  
  
> [!NOTE]
>  삽입 한 경우 `NULL`의문자열에 문자열을 마샬링 한 결과를 보장 되지 않습니다. 포함 된 `NULL`잘릴 문자열 하면 수 있습니다 또는 유지 될 수 있습니다.  
  
 마샬링 라이브러리 헤더 msclr 하위 디렉터리에서 include 디렉터리에 있습니다. 이 예제에는 포함 헤더 선언에 msclr 디렉터리를 포함 하는 방법을 보여 줍니다.  
  
 `#include "msclr\marshal_cppstd.h"`  
  
 마샬링 라이브러리는 고유한 마샬링 형식을 추가할 수 있도록 확장이 가능 합니다. 마샬링 라이브러리를 확장 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: 마샬링 라이브러리 확장명](../dotnet/how-to-extend-the-marshaling-library.md)합니다.  
  
 이전 버전에서 사용 하 여 데이터를 마샬링할 수 [플랫폼 호출](/dotnet/framework/interop/consuming-unmanaged-dll-functions)합니다. 에 대 한 자세한 내용은 `PInvoke`, 참조 [관리 코드에서 네이티브 함수 호출](../dotnet/calling-native-functions-from-managed-code.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C + + 지원 라이브러리](../dotnet/cpp-support-library.md)   
 [방법: 마샬링 라이브러리 확장](../dotnet/how-to-extend-the-marshaling-library.md)