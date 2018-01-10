---
title: 'marshal_context:: marshal_as | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- marshal_context::marshal_as
- marshal_context.marshal_as
- msclr.interop.marshal_context.marshal_as
- msclr::interop::marshal_context::marshal_as
dev_langs: C++
helpviewer_keywords: marshal_context class [C++], operations
ms.assetid: 24a1afee-51c0-497c-948c-f77fe43635c8
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e56e225d136fb02445eeeb398937adc075f2dae7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="marshalcontextmarshalas"></a>marshal_context::marshal_as
관리 되는 및 네이티브 데이터 형식 간에 변환 하려면 특정 데이터 개체에 대해 마샬링을 수행 합니다.  
  
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
 이 함수는 특정 데이터 개체에 대해 마샬링을 수행 합니다. 이 함수를 사용 하 여 테이블에 표시 된 변환이 있는 [개요의 c + + 마샬링](../dotnet/overview-of-marshaling-in-cpp.md)합니다.  
  
 지원 되지 않는 데이터 형식의 쌍 마샬링할 하려고 하면 `marshal_as` 오류가 생성 됩니다 [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) 컴파일 타임에 있습니다. 자세한 내용은이 오류와 함께 제공 된 메시지를 읽습니다. `C4996` 이상만 사용 되지 않는 함수에 대 한 오류는 생성 될 수 있습니다. 이 오류를 생성 하는 두 가지 조건은를 한 쌍의 지원 되지 않는 데이터 형식 마샬링하는 동안 하며 사용 하려고 `marshal_as` 변환 하는 컨텍스트가 필요 합니다.  
  
 마샬링 라이브러리 헤더 파일을 여러 개 구성 됩니다. 모든 변환 파일 하나만 필요 하지만 다른 변환 해야 하는 경우 추가 파일을 포함할 수 있습니다. 테이블 `Marshaling Overview in C++` 마샬링 파일 각 변환에 대 한 포함 되어야 합니다. 나타냅니다.  
  
## <a name="example"></a>예  
 이 예제에서 마샬링하기 위한 컨텍스트를 만듭니다.는 `System::String` 에 `const char *` 변수 형식입니다. 변환된 된 데이터 컨텍스트를 삭제 하는 줄 다음 유효한 되지 않습니다.  
  
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
  
## <a name="requirements"></a>요구 사항  
 **헤더 파일:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, 또는 \<msclr\marshal_atl.h >  
  
 **Namespace:** msclr::interop  
  
## <a name="see-also"></a>참고 항목  
 [C + + 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_as](../dotnet/marshal-as.md)   
 [marshal_context 클래스](../dotnet/marshal-context-class.md)