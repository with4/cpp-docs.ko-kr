---
title: '_bstr_t:: assign | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::Assign
dev_langs:
- C++
helpviewer_keywords:
- Assign method [C++]
ms.assetid: 2e209bbe-77ca-4598-86d5-6c2ea213f43c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a415f695f512a9d6263025fc6e45d5f9df754f80
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403909"
---
# <a name="bstrtassign"></a>_bstr_t::Assign
**Microsoft 전용**  
  
 복사본을 `BSTR` 에 `BSTR` 래핑되는 **_**`bstr_t`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void Assign(  
   BSTR s  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *s*  
 `BSTR`로 래핑된 `BSTR`로 복사되는 `_bstr_t`입니다.  
  
## <a name="remarks"></a>설명  
 **할당** 는 이진 복사, 즉, 전체 길이 `BSTR` 내용에 관계 없이 복사 됩니다.  
  
## <a name="example"></a>예  
  
```cpp 
// _bstr_t_Assign.cpp  
  
#include <comdef.h>  
#include <stdio.h>  
  
int main()  
{  
    // creates a _bstr_t wrapper  
    _bstr_t bstrWrapper;   
  
    // creates BSTR and attaches to it  
    bstrWrapper = "some text";  
    wprintf_s(L"bstrWrapper = %s\n",  
              static_cast<wchar_t*>(bstrWrapper));  
  
    // bstrWrapper releases its BSTR  
    BSTR bstr = bstrWrapper.Detach();  
    wprintf_s(L"bstrWrapper = %s\n",   
              static_cast<wchar_t*>(bstrWrapper));  
    // "some text"   
    wprintf_s(L"bstr = %s\n", bstr);  
  
    bstrWrapper.Attach(SysAllocString(OLESTR("SysAllocedString")));  
    wprintf_s(L"bstrWrapper = %s\n",   
              static_cast<wchar_t*>(bstrWrapper));  
  
    // assign a BSTR to our _bstr_t  
    bstrWrapper.Assign(bstr);  
    wprintf_s(L"bstrWrapper = %s\n",   
              static_cast<wchar_t*>(bstrWrapper));  
  
    // done with BSTR, do manual cleanup  
    SysFreeString(bstr);  
  
    // resuse bstr  
    bstr= SysAllocString(OLESTR("Yet another string"));  
    // two wrappers, one BSTR   
    _bstr_t bstrWrapper2 = bstrWrapper;     
  
    *bstrWrapper.GetAddress() = bstr;  
  
    // bstrWrapper and bstrWrapper2 do still point to BSTR  
    bstr = 0;     
    wprintf_s(L"bstrWrapper = %s\n",   
              static_cast<wchar_t*>(bstrWrapper));  
    wprintf_s(L"bstrWrapper2 = %s\n",   
              static_cast<wchar_t*>(bstrWrapper2));  
  
    // new value into BSTR  
    _snwprintf_s(bstrWrapper.GetBSTR(), 100, bstrWrapper.length(),  
                 L"changing BSTR");     
    wprintf_s(L"bstrWrapper = %s\n",   
              static_cast<wchar_t*>(bstrWrapper));  
    wprintf_s(L"bstrWrapper2 = %s\n",   
              static_cast<wchar_t*>(bstrWrapper2));  
}  
```  
  
```Output  
bstrWrapper = some text  
bstrWrapper = (null)  
bstr = some text  
bstrWrapper = SysAllocedString  
bstrWrapper = some text  
bstrWrapper = Yet another string  
bstrWrapper2 = some text  
bstrWrapper = changing BSTR  
bstrWrapper2 = some text  
```  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고자료  
 [_bstr_t 클래스](../cpp/bstr-t-class.md)