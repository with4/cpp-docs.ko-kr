---
title: _set_com_error_handler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- _set_com_error_handler function
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08d5df7893aa5390a6e577e3c26424864f7c3a8f
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465768"
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
 *pHandler*  
 대체 함수에 대한 포인터입니다.  
  
 *hr*  
 HRESULT 정보입니다.  
  
 *perrinfo*  
 `IErrorInfo` 개체  
  
## <a name="remarks"></a>설명  
 기본적으로 [_com_raise_error](../cpp/com-raise-error.md) 모든 COM 오류를 처리 합니다. 사용 하 여이 동작을 변경할 수 있습니다 **_set_com_error_handler** 사용자 고유의 오류 처리 함수를 호출 합니다.  
  
 대체 함수에는 `_com_raise_error`의 시그니처에 해당하는 시그니처가 있어야 합니다.  
  
## <a name="example"></a>예  
  
```cpp 
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
 **헤더:** \<comdef.h >  
  
 **Lib:** 경우는 **wchar_t is Native Type** 컴파일러 옵션이 설정 되어 있는 경우 comsuppw.lib 또는 comsuppwd.lib를 사용 합니다. 하는 경우 **wchar_t is Native Type** 해제가 comsupp.lib를 사용 합니다. 자세한 내용은 [/Zc:wchar_t(wchar_t는 네이티브 형식임)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)를 참조하세요.  
  
## <a name="see-also"></a>참고자료  
 [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)