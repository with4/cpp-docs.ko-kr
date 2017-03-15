---
title: "_bstr_t::Assign | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::Assign"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assign 메서드"
ms.assetid: 2e209bbe-77ca-4598-86d5-6c2ea213f43c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# _bstr_t::Assign
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `BSTR`을 **\_**`bstr_t`로 래핑된 `BSTR`로 복사합니다.  
  
## 구문  
  
```  
void Assign(  
   BSTR s  
);  
```  
  
#### 매개 변수  
 `s`  
 `_bstr_t`로 래핑된 `BSTR`로 복사되는 `BSTR`입니다.  
  
## 설명  
 `Assign`은 이진 복사를 수행합니다. 즉, `BSTR`의 전체 길이가 내용과 관계없이 복사됩니다.  
  
## 예제  
  
```  
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
  
  **bstrWrapper \= some text**  
**bstrWrapper \= \(null\)**  
**bstr \= some text**  
**bstrWrapper \= SysAllocedString**  
**bstrWrapper \= some text**  
**bstrWrapper \= Yet another string**  
**bstrWrapper2 \= some text**  
**bstrWrapper \= changing BSTR**  
**bstrWrapper2 \= some text**   
## Microsoft 전용 종료  
  
## 참고 항목  
 [\_bstr\_t 클래스](../cpp/bstr-t-class.md)