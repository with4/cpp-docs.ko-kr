---
title: "이진 출력 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "이진 데이터, 이진 출력 파일"
  - "파일[C++], 이진 출력 파일"
  - "I/O[C++], 이진 출력 파일"
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 이진 출력 파일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Streams were originally designed for text, so the default output mode is text.  In text mode, the newline character \(hexadecimal 10\) expands to a carriage return–linefeed \(16\-bit only\).  The expansion can cause problems, as shown here:  
  
```  
// binary_output_files.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
int iarray[2] = { 99, 10 };  
int main( )  
{  
    ofstream os( "test.dat" );  
    os.write( (char *) iarray, sizeof( iarray ) );  
}  
```  
  
 You might expect this program to output the byte sequence { 99, 0, 10, 0 }; instead, it outputs { 99, 0, 13, 10, 0 }, which causes problems for a program expecting binary input.  If you need true binary output, in which characters are written untranslated, you could specify binary output by using the [ofstream](../Topic/ofstream.md) constructor mode argument:  
  
```  
// binary_output_files2.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
int iarray[2] = { 99, 10 };  
  
int main()  
{  
   ofstream ofs ( "test.dat", ios_base::binary );  
  
   // Exactly 8 bytes written  
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );   
}  
```  
  
## 참고 항목  
 [Output Streams](../standard-library/output-streams.md)