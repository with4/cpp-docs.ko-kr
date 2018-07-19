---
title: _com_raise_error | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_raise_error
dev_langs:
- C++
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f38a0d97b90f1512e5f16b3bd147bda3e0614e4f
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944476"
---
# <a name="comraiseerror"></a>_com_raise_error
**Microsoft 전용**  
  
 Throw 된 [_com_error](../cpp/com-error-class.md) 오류에 대 한 응답에서입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
void __stdcall _com_raise_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = 0  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *hr*  
 HRESULT 정보입니다.  
  
 *perrinfo*  
 `IErrorInfo` 개체  
  
## <a name="remarks"></a>설명  
 `_com_raise_error`에 정의 되어 있는 \<comdef.h >에서 동일한 이름과 프로토타입의 사용자 작성 버전으로 대체할 수 있습니다. 이는 `#import`를 사용하고 C++ 예외 처리는 사용하지 않으려는 경우 실행할 수 있습니다. 경우 사용자 버전에서 `_com_raise_error` 하기로 결정할 수는 `longjmp` 또는 메시지 상자를 표시 하 고 중지 합니다. 컴파일러 COM 지원 코드가 반환을 예상하고 있지 않기 때문에 사용자 버전은 반환할 수 없습니다.  
  
 사용할 수도 있습니다 [_set_com_error_handler](../cpp/set-com-error-handler.md) 기본 오류 처리 함수를 교체할 수 있습니다.  
  
 기본적으로 `_com_raise_error`는 다음과 같이 정의됩니다.  
  
```cpp  
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {  
   throw _com_error(hr, perrinfo);  
}  
```  
  
**Microsoft 전용 종료**  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<comdef.h >  
  
 **Lib:** 경우는 **wchar_t is Native Type** 컴파일러 옵션이 설정 되어 있는 경우 comsuppw.lib 또는 comsuppwd.lib를 사용 합니다. 하는 경우 **wchar_t is Native Type** 해제가 comsupp.lib를 사용 합니다. 자세한 내용은 [/Zc:wchar_t(wchar_t는 네이티브 형식임)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)   
 [_set_com_error_handler](../cpp/set-com-error-handler.md)