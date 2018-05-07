---
title: '방법: 텍스트 파일 읽기 (C + + /cli CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- reading text files
- text files, reading
ms.assetid: 80551c01-d769-4b6d-8db7-fd53bde21b62
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c350ea9cd8b71378d059a93ac80ca808d4f48790
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-a-text-file-ccli"></a>방법: 텍스트 파일 읽기(C++/CLI)
다음 코드 예제에서는 열고 사용 하 여 한 번에는 한 줄씩 텍스트 파일을 읽는 방법을 보여 줍니다.는 <xref:System.IO.StreamReader> 에 정의 된 클래스는 <xref:System.IO?displayProperty=fullName> 네임 스페이스입니다. 텍스트 파일을이 클래스의 인스턴스는 다음의 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName> 각 줄을 검색 메서드를 사용 합니다.  
  
 이 코드 예제에서 명명 된 textfile.txt 및 텍스트를 포함 하는 파일을 읽습니다. 이런이 종류의 파일에 대 한 정보를 참조 하십시오. [하는 방법: 텍스트 파일 쓰기 (C + + /cli CLI)](../dotnet/how-to-write-a-text-file-cpp-cli.md)합니다.  
  
## <a name="example"></a>예제  
  
```  
// text_read.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   String^ fileName = "textfile.txt";  
   try   
   {  
      Console::WriteLine("trying to open file {0}...", fileName);  
      StreamReader^ din = File::OpenText(fileName);  
  
      String^ str;  
      int count = 0;  
      while ((str = din->ReadLine()) != nullptr)   
      {  
         count++;  
         Console::WriteLine("line {0}: {1}", count, str );  
      }  
   }  
   catch (Exception^ e)  
   {  
      if (dynamic_cast<FileNotFoundException^>(e))  
         Console::WriteLine("file '{0}' not found", fileName);  
      else  
         Console::WriteLine("problem reading file '{0}'", fileName);  
   }  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [파일 및 스트림 I/O](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)