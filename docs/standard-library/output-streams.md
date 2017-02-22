---
title: "Output Streams | Microsoft Docs"
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
  - "출력 스트림"
ms.assetid: b49410e3-5caa-4153-9d0d-c4266408dc83
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Output Streams
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

An output stream object is a destination for bytes.  The three most important output stream classes are `ostream`, `ofstream`, and `ostringstream`.  
  
 The `ostream` class, through the derived class `basic_ostream`, supports the predefined stream objects:  
  
-   `cout` standard output  
  
-   `cerr` standard error with limited buffering  
  
-   `clog` similar to `cerr` but with full buffering  
  
 Objects are rarely constructed from `ostream`; predefined objects are generally used.  In some cases, you can reassign predefined objects after program startup.  The `ostream` class, which can be configured for buffered or unbuffered operation, is best suited to sequential text\-mode output.  All functionality of the base class, `ios`, is included in `ostream`.  If you construct an object of class `ostream`, you must specify a `streambuf` object to the constructor.  
  
 The `ofstream` class supports disk file output.  If you need an output\-only disk, construct an object of class `ofstream`.  You can specify whether `ofstream` objects accept binary or text\-mode data when constructing the `ofstream` object or when calling the `open` member function of the object.  Many formatting options and member functions apply to `ofstream` objects, and all functionality of the base classes `ios` and `ostream` is included.  
  
 If you specify a filename in the constructor, that file is automatically opened when the object is constructed.  Otherwise, you can use the `open` member function after invoking the default constructor.  
  
 Like the run\-time function `sprintf_s`, the `ostringstream` class supports output to in\-memory strings.  To create a string in memory by using I\/O stream formatting, construct an object of class `ostringstream`.  
  
## 단원 내용  
 [출력 스트림 개체 생성](../standard-library/constructing-output-stream-objects.md)  
  
 [삽입 연산자 사용 및 형식 제어](../standard-library/using-insertion-operators-and-controlling-format.md)  
  
 [Output File Stream Member 함수](../standard-library/output-file-stream-member-functions.md)  
  
 [버퍼링 효과](../standard-library/effects-of-buffering.md)  
  
 [이진 출력 파일](../standard-library/binary-output-files.md)  
  
 [고유 클래스에 대해 \<\< 연산자 오버로드](../standard-library/overloading-the-output-operator-for-your-own-classes.md)  
  
 [인수 없이 고유 조작자 작성](../standard-library/writing-your-own-manipulators-without-arguments.md)  
  
## 참고 항목  
 [\<ostream\> Members](http://msdn.microsoft.com/ko-kr/a5afd034-0e3c-41ee-bbd7-468d9188da1d)   
 [ofstream](../Topic/ofstream.md)   
 [ostringstream](../Topic/ostringstream.md)   
 [basic\_ostream Members](http://msdn.microsoft.com/ko-kr/82e5cc91-7c0c-4950-a8ce-ac779cfbbd93)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)