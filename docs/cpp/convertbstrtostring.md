---
title: ConvertBSTRToString | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: ConvertBSTRToString
dev_langs: C++
helpviewer_keywords: ConvertBSTRToString function
ms.assetid: ab6ce555-3d75-4e9c-9cb8-ada6d8ce43b1
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a7f3463e34c17bcde4f64b89e1ae083228317293
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="convertbstrtostring"></a>ConvertBSTRToString
**Microsoft 전용**  
  
 변환 된 `BSTR` 값을 한 **char \*** 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      char* __stdcall ConvertBSTRToString(  
   BSTR pSrc  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pSrc`  
 BSTR 변수입니다.  
  
## <a name="remarks"></a>설명  
 `ConvertBSTRToString`은 삭제해야 하는 문자열을 할당합니다.  
  
## <a name="example"></a>예  
  
```  
// ConvertBSTRToString.cpp  
#include <comutil.h>  
#include <stdio.h>  
  
#pragma comment(lib, "comsuppw.lib")  
  
int main() {  
   BSTR bstrText = ::SysAllocString(L"Test");  
   wprintf_s(L"BSTR text: %s\n", bstrText);  
  
   char* lpszText2 = _com_util::ConvertBSTRToString(bstrText);  
   printf_s("char * text: %s\n", lpszText2);  
  
   SysFreeString(bstrText);  
   delete[] lpszText2;  
}  
```  
  
```Output  
BSTR text: Test  
char * text: Test  
```  
  
**Microsoft 전용 종료**  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<comutil.h > 합니다.  
  
 **Lib:** 에서는 comsuppw.lib 또는 comsuppwd.lib (참조 [/zc: wchar_t (wchar_t는 네이티브 형식임)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 자세한 내용은)  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)