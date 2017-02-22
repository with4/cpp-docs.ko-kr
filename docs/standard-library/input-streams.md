---
title: "Input Streams | Microsoft Docs"
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
  - "데이터[C++], 입력 스트림에서 읽기"
  - "입력 스트림 개체"
  - "입력 스트림"
  - "데이터 읽기[C++], 입력 스트림에서"
ms.assetid: f14d8954-8f8c-4c3c-8b99-14ddb3683f94
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Input Streams
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

An input stream object is a source of bytes.  The three most important input stream classes are [istream](http://msdn.microsoft.com/ko-kr/6801779e-260e-416d-b4ec-fef5ff1b2371), [ifstream](../Topic/ifstream.md), and [istringstream](../Topic/istringstream.md).  
  
 The `istream` class is best used for sequential text\-mode input.  You can configure objects of class `istream` for buffered or unbuffered operation.  All functionality of the base class, `ios`, is included in `istream`.  You will rarely construct objects from class `istream`.  Instead, you will generally use the predefined `cin` object, which is actually an object of class [ostream](../standard-library/ostream.md).  In some cases, you can assign `cin` to other stream objects after program startup.  
  
 The `ifstream` class supports disk file input.  If you need an input\-only disk file, construct an object of class `ifstream`.  You can specify binary or text\-mode data.  If you specify a filename in the constructor, the file is automatically opened when the object is constructed.  Otherwise, you can use the `open` function after invoking the default constructor.  Many formatting options and member functions apply to `ifstream` objects.  All functionality of the base classes `ios` and `istream` is included in `ifstream`.  
  
 Like the library function `sscanf_s`, the `istringstream` class supports input from in\-memory strings.  To extract data from a character array that has a null terminator, allocate and initialize the string, then construct an object of class `istringstream`.  
  
## 단원 내용  
 [입력 스트림 개체 생성](../standard-library/constructing-input-stream-objects.md)  
  
 [추출 연산자 사용](../standard-library/using-extraction-operators.md)  
  
 [추출 오류 테스트](../standard-library/testing-for-extraction-errors.md)  
  
 [입력 스트림 조작자](../standard-library/input-stream-manipulators.md)  
  
 [입력 스트림 멤버 함수](../standard-library/input-stream-member-functions.md)  
  
 [고유 클래스에 대해 \>\> 연산자 오버로드](../standard-library/overloading-the-input-operator-for-your-own-classes.md)  
  
## 참고 항목  
 [iostream 프로그래밍](../standard-library/iostream-programming.md)