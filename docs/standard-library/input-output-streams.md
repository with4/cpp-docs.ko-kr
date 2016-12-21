---
title: "입력/출력 스트림 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "I/O[C++], 스트림"
  - "스트림 I/O"
ms.assetid: 21a97566-91a7-42d6-b2f8-a4c16bc926f1
caps.latest.revision: 11
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 입력/출력 스트림
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`basic_iostream`, which is defined in the header file \<istream\>, is the class template for objects that handle both input and output character\-based I\/O streams.  
  
 There are two typedefs that define character\-specific specializations of `basic_iostream` and can help make code easier to read: `iostream` \(not to be confused with the header file \<iostream\>\) is an I\/O stream that is based on `basic_iostream<char>`; `wiostream` is an I\/O stream that is based on `basic_iostream<wchar_t>`.  
  
 자세한 내용은 [basic\_iostream 클래스](../standard-library/basic-iostream-class.md), [iostream](../Topic/iostream.md) 및 [wiostream](../Topic/wiostream.md)를 참조하십시오.  
  
 Deriving from `basic_iostream` is the class template `basic_fstream`, which is used to stream character data to and from files.  
  
 There also are typedefs that provide character\-specific specializations of `basic_fstream`.  They are `fstream`, which is a file I\/O stream that is based on `char`, and `wfstream`, which is a file I\/O stream that is based on `wchar_t`.  자세한 내용은 [basic\_fstream 클래스](../standard-library/basic-fstream-class.md), [fstream](../Topic/fstream.md) 및 [wfstream](../Topic/wfstream.md)를 참조하십시오.  Using these typedefs requires the inclusion of the header file \<fstream\>.  
  
> [!NOTE]
>  When a `basic_fstream` object is used to perform file I\/O, although the underlying buffer contains separately designated positions for reading and writing, the current input and current output positions are tied together, and therefore, reading some data moves the output position.  
  
 The class template `basic_stringstream` and its common specialization, `stringstream`, are often used to work with I\/O stream objects to insert and extract character data.  자세한 내용은 [basic\_stringstream 클래스](../standard-library/basic-stringstream-class.md)을 참조하십시오.  
  
## 참고 항목  
 [stringstream](../Topic/stringstream.md)   
 [basic\_stringstream 클래스](../standard-library/basic-stringstream-class.md)   
 [\<sstream\>](../standard-library/sstream.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [C\+\+ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)