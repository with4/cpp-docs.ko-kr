---
title: _set_com_error_handler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- _set_com_error_handler function
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 626227fb9c5162e5b9fc72fc64348b75ecb27e44
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="setcomerrorhandler"></a>_set_com_error_handler
**Microsoft 전용**  
  
 COM 오류 처리에 사용되는 기본 함수를 대체합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __stdcall _set_com_error_handler(  
   void (__stdcall *pHandler)(  
      HRESULT hr,   
      IErrorInfo* perrinfo  
   )  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pHandler`  
 대체 함수에 대한 포인터입니다.  
  
 `hr`  
 `HRESULT` 정보입니다.  
  
 `perrinfo`  
 `IErrorInfo` 개체  
  
## <a name="remarks"></a>설명  
 기본적으로 [_com_raise_error](../cpp/com-raise-error.md) 모든 COM 오류를 처리 합니다. `_set_com_error_handler`를 사용하여 이 동작을 변경하여 사용자 고유의 오류 처리 함수를 호출할 수 있습니다.  
  
 대체 함수에는 `_com_raise_error`의 시그니처에 해당하는 시그니처가 있어야 합니다.  
  
## <a name="example"></a>예제  
  
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
  
```Output  
Exception raised: Unable to establish the connection!  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** comdef.h  
  
 **Lib:** 경우는 **wchar_t is Native Type** 컴파일러 옵션이 설정 되어 있는 경우 comsuppw.lib 또는 comsuppwd.lib를 사용 합니다. 경우 **wchar_t is Native Type** 해제, comsupp.lib를 사용 합니다. 자세한 내용은 [/Zc:wchar_t(wchar_t는 네이티브 형식임)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)
