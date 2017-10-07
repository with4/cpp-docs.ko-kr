---
title: _com_raise_error | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_raise_error
dev_langs:
- C++
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 1f2072a6f3a6f78bc6751e39e0c79d978845fe97
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="comraiseerror"></a>_com_raise_error
**Microsoft 전용**  
  
 throw 한 [_com_error](../cpp/com-error-class.md) 는 오류에 대응 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      void __stdcall _com_raise_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = 0  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hr`  
 `HRESULT` 정보입니다.  
  
 `perrinfo`  
 **IErrorInfo** 개체입니다.  
  
## <a name="remarks"></a>설명  
 comdef.h에서 정의된 `_com_raise_error`는 동일한 이름과 프로토타입의 사용자 작성 버전으로 교체할 수 있습니다. 이는 `#import`를 사용하고 C++ 예외 처리는 사용하지 않으려는 경우 실행할 수 있습니다. 사례를 사용자 버전의에서 **_com_raise_error** 수행 하도록 결정할 수도 `longjmp` 또는 메시지 상자를 표시 하 고 중지 합니다. 컴파일러 COM 지원 코드가 반환을 예상하고 있지 않기 때문에 사용자 버전은 반환할 수 없습니다.  
  
 사용할 수도 있습니다 [_set_com_error_handler](../cpp/set-com-error-handler.md) 기본 오류 처리 함수를 교체할 수 있습니다.  
  
 기본적으로 `_com_raise_error`는 다음과 같이 정의됩니다.  
  
```  
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {  
   throw _com_error(hr, perrinfo);  
}  
```  
  
**Microsoft 전용 종료**  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** comdef.h  
  
 **Lib:** 경우는 **wchar_t is Native Type** 컴파일러 옵션이 설정 되어 있는 경우 comsuppw.lib 또는 comsuppwd.lib를 사용 합니다. 경우 **wchar_t is Native Type** 해제, comsupp.lib를 사용 합니다. 자세한 내용은 [/Zc:wchar_t(wchar_t는 네이티브 형식임)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)   
 [_set_com_error_handler](../cpp/set-com-error-handler.md)
