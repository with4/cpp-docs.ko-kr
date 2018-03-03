---
title: ConvertStringToBSTR | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ConvertStringToBSTR
dev_langs:
- C++
helpviewer_keywords:
- ConvertStringToBSTR function
ms.assetid: 071f9b3b-9643-4e06-a1e5-de96ed15bab2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b396930f6a16c3773b917dc21b2c61525350f397
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="convertstringtobstr"></a>ConvertStringToBSTR
**Microsoft 전용**  
  
 변환 된 **char \***  값을 한 `BSTR`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      BSTR __stdcall ConvertStringToBSTR(  
   const char* pSrc  
)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pSrc`  
 A **char \***  변수입니다.  
  
## <a name="example"></a>예  
  
```  
// ConvertStringToBSTR.cpp  
#include <comutil.h>  
#include <stdio.h>  
  
#pragma comment(lib, "comsuppw.lib")  
#pragma comment(lib, "kernel32.lib")  
  
int main() {  
   char* lpszText = "Test";  
   printf_s("char * text: %s\n", lpszText);  
  
   BSTR bstrText = _com_util::ConvertStringToBSTR(lpszText);  
   wprintf_s(L"BSTR text: %s\n", bstrText);  
  
   SysFreeString(bstrText);  
}  
```  
  
```Output  
char * text: Test  
BSTR text: Test  
```  
  
**Microsoft 전용 종료**  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<comutil.h >  
  
 **Lib:** 에서는 comsuppw.lib 또는 comsuppwd.lib (참조 [/zc: wchar_t (wchar_t는 네이티브 형식임)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 자세한 내용은)  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)