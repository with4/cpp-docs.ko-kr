---
title: '방법: 표준 문자열을 system:: string으로 변환 | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++ Standard Library, converting strings to System::String
- string conversion [C++], C++ Standard Library string
- strings [C++], converting
ms.assetid: 1fde79a0-9d0b-44e5-981b-e8f2676c199d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4910ca322b71e8570aebd9196b106680454fd261
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-convert-standard-string-to-systemstring"></a>방법: 표준 문자열을 System::String으로 변환
이 항목에서는 c + + 표준 라이브러리 문자열로 변환 하는 방법을 ([\<문자열 >](../standard-library/string.md))에 <xref:System.String>합니다.  
  
## <a name="example"></a>예제  
  
```  
// convert_standard_string_to_system_string.cpp  
// compile with: /clr  
#include <string>  
#include <iostream>  
using namespace System;  
using namespace std;  
  
int main() {  
   string str = "test";  
   cout << str << endl;  
   String^ str2 = gcnew String(str.c_str());  
   Console::WriteLine(str2);  
  
   // alternatively  
   String^ str3 = gcnew String(str.c_str());  
   Console::WriteLine(str3);  
}  
```  
  
```Output  
test  
test  
test  
```  
  
## <a name="see-also"></a>참고 항목  
 [C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)