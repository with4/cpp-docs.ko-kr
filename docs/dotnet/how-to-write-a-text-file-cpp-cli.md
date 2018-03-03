---
title: "방법: 텍스트 파일 쓰기 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- files [C++], text
- text files, writing in C++
ms.assetid: 39ecdba6-84e0-485c-a202-84cf6d7b8d4a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 58b53159bab17ef0fddf5b26606889f89412856e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-write-a-text-file-ccli"></a>방법: 텍스트 파일 쓰기(C++/CLI)
다음 코드 예제에서는 텍스트 파일을 만들고 사용 하 여 텍스트를 쓰는 데는 <xref:System.IO.StreamWriter> 에 정의 된 클래스는 <xref:System.IO> 네임 스페이스입니다. <xref:System.IO.StreamWriter> 생성자 만들 파일의 이름을 사용 합니다. 파일이 있으면 덮어씁니다 (두 번째 True를 전달 하지 않으면 <xref:System.IO.StringWriter> 생성자 인수).  
  
 파일은 사용 하 여 제출 다음는 <xref:System.IO.StreamWriter.Write%2A> 및 <xref:System.IO.TextWriter.WriteLine%2A> 함수입니다.  
  
## <a name="example"></a>예  
  
```  
// text_write.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
  
int main()   
{  
   String^ fileName = "textfile.txt";  
  
   StreamWriter^ sw = gcnew StreamWriter(fileName);  
   sw->WriteLine("A text file is born!");  
   sw->Write("You can use WriteLine");  
   sw->WriteLine("...or just Write");  
   sw->WriteLine("and do {0} output too.", "formatted");  
   sw->WriteLine("You can also send non-text objects:");  
   sw->WriteLine(DateTime::Now);  
   sw->Close();  
   Console::WriteLine("a new file ('{0}') has been written", fileName);  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [파일 및 스트림 I/O](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)