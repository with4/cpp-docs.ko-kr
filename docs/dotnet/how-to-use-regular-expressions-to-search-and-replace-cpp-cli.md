---
title: '방법: 정규식을 사용 하 여 검색 하 고 바꿀 (C + + /cli CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- search and replace
- Replace method
- regular expressions [C++], search and replace
ms.assetid: 12fe3e18-fe10-4b25-a221-19dc5eab3821
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: feb64670accef1cdcc5eedf9aa2b081dc41615b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-regular-expressions-to-search-and-replace-ccli"></a>방법: 정규식을 사용한 찾기 및 바꾸기(C++/CLI)
다음 코드 예제에서는 어떻게 정규식 클래스 <xref:System.Text.RegularExpressions.Regex> 찾기 및 바꾸기를 수행 데 사용할 수 있습니다. 이러한 용도로 <xref:System.Text.RegularExpressions.Regex.Replace%2A> 메서드. 입력으로 사용 되는 버전은 두 문자열: 문자열을 수정할 수 및 (있는 경우)는 섹션이 대신 삽입할 문자열에 지정 된 패턴과 일치 하는 <xref:System.Text.RegularExpressions.Regex> 개체입니다.  
  
 이 코드는 문자열에 있는 모든 숫자 밑줄 (_)로 바꾸고 보다 효과적으로 제거 빈 문자열을 대체 합니다. 한 번에 같은 기능을 수행할 수 있습니다 하지만 데모용으로 여기서 두 단계는 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// regex_replace.cpp  
// compile with: /clr  
#using <System.dll>  
using namespace System::Text::RegularExpressions;  
using namespace System;  
  
int main()  
{  
   String^ before = "The q43uick bro254wn f0ox ju4mped";  
   Console::WriteLine("original  : {0}", before);  
  
   Regex^ digitRegex = gcnew Regex("(?<digit>[0-9])");  
   String^ after = digitRegex->Replace(before, "_");  
   Console::WriteLine("1st regex : {0}", after);  
  
   Regex^ underbarRegex = gcnew Regex("_");  
   String^ after2 = underbarRegex->Replace(after, "");  
   Console::WriteLine("2nd regex : {0}", after2);  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [.NET Framework 정규식](/dotnet/standard/base-types/regular-expressions)   
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)