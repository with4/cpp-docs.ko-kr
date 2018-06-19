---
title: 정규식을 사용 하 여 유효성을 검사할 서식 지정 (C + + /cli CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], formatting
- data [C++], formatting
- regular expressions [C++], validating data formatting
ms.assetid: 225775c3-3efc-4734-bde2-1fdf73e3d397
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 59a553ac2d58f9304fce3961aa8212c33b26643a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129618"
---
# <a name="how-to-use-regular-expressions-to-validate-data-formatting-ccli"></a>방법: 정규식을 사용하여 데이터 형식 유효성 검사(C++/CLI)
다음 코드 예제에서는 문자열의 서식을 확인 하려면 정규식 사용을 보여 줍니다. 다음 코드 예제에서 문자열 올바른 전화 번호를 포함 해야 합니다. 다음 코드 예제에서는 문자열을 사용 하 여 "\d{3}-\d{3}-\d{4}"를 나타내는 각 필드는 올바른 전화 번호를 나타냅니다. 문자열에 "d"는 숫자를 나타냅니다 하 고 각 "d" 뒤에 있는 인수 존재 해야 하는 자릿수를 나타냅니다. 이 경우에 수는 대시로 구분 하는 데 필요 합니다.  
  
## <a name="example"></a>예제  
  
```  
// regex_validate.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ number =   
   {  
      "123-456-7890",   
      "444-234-22450",   
      "690-203-6578",   
      "146-893-232",  
      "146-839-2322",  
      "4007-295-1111",   
      "407-295-1111",   
      "407-2-5555",   
   };  
  
   String^ regStr = "^\\d{3}-\\d{3}-\\d{4}$";  
  
   for ( int i = 0; i < number->Length; i++ )  
   {  
      Console::Write( "{0,14}", number[i] );  
  
      if ( Regex::IsMatch( number[i], regStr ) )  
         Console::WriteLine(" - valid");  
      else  
         Console::WriteLine(" - invalid");  
   }  
   return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [.NET Framework 정규식](/dotnet/standard/base-types/regular-expressions)   
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)