---
title: '방법: 정규식을 사용 하 여 데이터 필드를 추출 하 (C + + /cli CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], extracting data from
- formatted strings [C++]
- regular expressions [C++], extracting data fields
- data [C++], extracting from strings
ms.assetid: b581d9b6-630e-48fa-94fe-20b0f7b89b06
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 20e1139ccee0c3cc1533f42fb1b9e1eafaca3afd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-regular-expressions-to-extract-data-fields-ccli"></a>방법: 정규식을 사용하여 데이터 필드 추출(C++/CLI)
다음 코드 예제에서는 데이터를 추출 하는 형식이 지정 된 문자열에서 정규식의 사용을 보여 줍니다. 다음 코드 예제에서는 <xref:System.Text.RegularExpressions.Regex> 전자 메일 주소에 해당 하는 패턴을 지정 하는 클래스입니다. 이 패턴이 사용자 전자 메일 주소 각각의 호스트 이름 부분을 검색 하는 데 사용할 수 있는 필드 식별자를 포함 합니다. <xref:System.Text.RegularExpressions.Match> 클래스 실제 패턴 일치를 수행 하는 데 사용 됩니다. 지정 된 전자 메일 주소를 유효한 경우 사용자 이름 및 호스트 이름을 추출 되 고 표시 합니다.  
  
## <a name="example"></a>예제  
  
```  
// Regex_extract.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace System::Text::RegularExpressions;  
  
int main()  
{  
    array<String^>^ address=  
    {  
        "jay@southridgevideo.com",  
        "barry@adatum.com",  
        "treyresearch.net",  
        "karen@proseware.com"  
    };  
  
    Regex^ emailregex = gcnew Regex("(?<user>[^@]+)@(?<host>.+)");  
  
    for (int i=0; i<address->Length; i++)  
    {  
        Match^ m = emailregex->Match( address[i] );  
        Console::Write("\n{0,25}", address[i]);  
  
        if ( m->Success )   
        {  
            Console::Write("   User='{0}'",   
            m->Groups["user"]->Value);  
            Console::Write("   Host='{0}'",   
            m->Groups["host"]->Value);  
        }  
        else   
            Console::Write("   (invalid email address)");  
        }  
  
    Console::WriteLine("");  
    return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [.NET Framework 정규식](/dotnet/standard/base-types/regular-expressions)   
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)