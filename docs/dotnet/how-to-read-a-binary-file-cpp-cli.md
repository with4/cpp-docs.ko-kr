---
title: '방법: 이진 파일 읽기 (C + + /cli CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- files [C++], binary
- binary files, reading in C++
ms.assetid: 41ad9ad1-5cac-489c-874e-4bb3a649073a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8411971c8bca79d9cb1809481b5a6be61b052262
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-a-binary-file-ccli"></a>방법: 이진 파일 읽기(C++/CLI)
다음 코드 예제에는 두 개의 클래스에서 사용 하 여 파일에서 이진 데이터를 읽는 방법을 보여 줍니다는 <xref:System.IO?displayProperty=fullName> 네임 스페이스: <xref:System.IO.FileStream> 및 <xref:System.IO.BinaryReader>합니다. <xref:System.IO.FileStream> 실제 파일을 나타냅니다. <xref:System.IO.BinaryReader> 이진 액세스를 허용 하는 스트림에 대 한 인터페이스를 제공 합니다.  
  
 코드 예제에서는 이름이 data.bin 및 이진 형식에서 정수를 포함 하는 파일을 읽습니다. 이런이 종류의 파일에 대 한 정보를 참조 하십시오. [하는 방법: 이진 파일 쓰기 (C + + /cli CLI)](../dotnet/how-to-write-a-binary-file-cpp-cli.md)합니다.  
  
## <a name="example"></a>예제  
  
```  
// binary_read.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()   
{  
   String^ fileName = "data.bin";  
   try  
   {  
      FileStream^ fs = gcnew FileStream(fileName, FileMode::Open);  
      BinaryReader^ br = gcnew BinaryReader(fs);  
  
      Console::WriteLine("contents of {0}:", fileName);  
      while (br->BaseStream->Position < br->BaseStream->Length)  
         Console::WriteLine(br->ReadInt32().ToString());  
  
      fs->Close( );  
   }  
   catch (Exception^ e)  
   {  
      if (dynamic_cast<FileNotFoundException^>(e))  
         Console::WriteLine("File '{0}' not found", fileName);  
      else  
         Console::WriteLine("Exception: ({0})", e);  
      return -1;  
   }  
   return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [파일 및 스트림 I/O](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)