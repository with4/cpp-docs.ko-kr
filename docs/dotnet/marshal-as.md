---
title: marshal_as | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- marshal_as
- msclr.interop.marshal_as
- msclr::interop::marshal_as
dev_langs:
- C++
helpviewer_keywords:
- marshal_as template [C++]
ms.assetid: 2ed717da-2b11-41e5-981d-47d251771989
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ebca4a94fa48feb4ff5fb897293303a395ac4eb8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33133781"
---
# <a name="marshalas"></a>marshal_as
이 메서드는 네이티브 및 관리 환경 간에 데이터를 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
To_Type marshal_as<To_Type>(  
   From_Type input   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `input`  
 마샬링할 하려는 값을 `To_Type` 변수입니다.  
  
## <a name="return-value"></a>반환 값  
 형식의 변수 `To_Type` 의 변환 된 값 즉 `input`합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 네이티브 및 관리 되는 형식 간에 데이터를 변환 하는 간편한 방법입니다. 지원 되는 데이터 형식을 확인 하려면 참조 [개요의 c + + 마샬링](../dotnet/overview-of-marshaling-in-cpp.md)합니다. 데이터 변환 중 일부는 컨텍스트가 필요합니다. 사용 하 여 이러한 데이터 형식을 변환할 수는 [marshal_context 클래스](../dotnet/marshal-context-class.md)합니다.  
  
 지원 되지 않는 데이터 형식의 쌍 마샬링할 하려고 하면 `marshal_as` 오류가 생성 됩니다 [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) 컴파일 타임에 있습니다. 자세한 내용은이 오류와 함께 제공 된 메시지를 읽습니다. `C4996` 이상만 사용 되지 않는 함수에 대 한 오류는 생성 될 수 있습니다. 이러한 예로 한 쌍의 지원 되지 않는 데이터 형식 마샬링하 려 합니다.  
  
 마샬링 라이브러리 헤더 파일을 여러 개 구성 됩니다. 모든 변환 파일 하나만 필요 하지만 다른 변환 해야 하는 경우 추가 파일을 포함할 수 있습니다. 어떤 변환에는 연결 된 파일을 보려면 테이블에 확인 `Marshaling Overview`합니다. 에 관계 없이 어떤 변환의 원하는 작업을 수행 하는 네임 스페이스 요구 사항을 항상 적용 합니다.  
  
## <a name="example"></a>예제  
 이 예제에서 마샬링하는 `const char*` 에 `System::String` 변수 형식입니다.  
  
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
  
## <a name="requirements"></a>요구 사항  
 **헤더 파일:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, 또는 \<msclr\marshal_atl.h >  
  
 **Namespace:** msclr::interop  
  
## <a name="see-also"></a>참고 항목  
 [C + + 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_context 클래스](../dotnet/marshal-context-class.md)