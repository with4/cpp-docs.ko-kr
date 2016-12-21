---
title: "What a Stream Is | Microsoft Docs"
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
  - "데이터[C++], 읽기"
  - "데이터 읽기[C++], iostream 프로그래밍"
  - "스트림[C++]"
  - "스트림[C++], iostream 클래스"
ms.assetid: a7e661e9-6cd1-4543-a9a4-c58ee9fd32f3
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# What a Stream Is
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Like C, C\+\+ does not have built\-in input\/output capability.  All C\+\+ compilers, however, come bundled with a systematic, object\-oriented I\/O package, known as the iostream classes.  The stream is the central concept of the iostream classes.  You can think of a stream object as a smart file that acts as a source and destination for bytes.  A stream's characteristics are determined by its class and by customized insertion and extraction operators.  
  
 Through device drivers, the disk operating system deals with the keyboard, screen, printer, and communication ports as extended files.  The iostream classes interact with these extended files.  Built\-in classes support reading from and writing to memory with syntax identical to that for disk I\/O, which makes it easy to derive stream classes.  
  
## 단원 내용  
 [입력\/출력 대체](../standard-library/input-output-alternatives.md)  
  
## 참고 항목  
 [iostream 프로그래밍](../standard-library/iostream-programming.md)