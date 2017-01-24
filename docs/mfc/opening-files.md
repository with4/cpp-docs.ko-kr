---
title: "파일 열기 | Microsoft Docs"
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
  - "CFile 클래스, 변수"
  - "예제[MFC], 파일 열기"
  - "예외 처리[C++], 파일 열기"
  - "예외 처리[C++], 파일을 열 때"
  - "파일 개체[C++]"
  - "파일[C++], 열기"
  - "MFC[C++], 파일 작업"
  - "Open 호출"
  - "Open 멤버 함수"
  - "Open 메서드, CFile 클래스"
  - "파일 열기"
  - "파일 열기, 예외 처리"
  - "파일 열기, MFC"
ms.assetid: a991b8ec-b04a-4766-b47e-7485b5dd0b01
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 파일 열기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In MFC, the most common way to open a file is a two\-stage process.  
  
#### To open a file  
  
1.  Create the file object without specifying a path or permission flags.  
  
     You usually create a file object by declaring a [CFile](../mfc/reference/cfile-class.md) variable on the stack frame.  
  
2.  Call the [Open](../Topic/CFile::Open.md) member function for the file object, supplying a path and permission flags.  
  
     The return value for `Open` will be nonzero if the file was opened successfully or 0 if the specified file could not be opened.  The `Open` member function is prototyped as follows:  
  
     `virtual BOOL Open( LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL );`  
  
     The open flags specify which permissions, such as read\-only, you want for the file.  The possible flag values are defined as enumerated constants within the `CFile` class, so they are qualified with "`CFile::`" as in `CFile::modeRead`.  Use the `CFile::modeCreate` flag if you want to create the file.  
  
 The following example shows how to create a new file with read\/write permission \(replacing any previous file with the same path\):  
  
 [!code-cpp[NVC_MFCFiles#1](../mfc/codesnippet/CPP/opening-files_1.cpp)]  
  
> [!NOTE]
>  This example creates and opens a file.  If there are problems, the `Open` call can return a `CFileException` object in its last parameter, as shown here.  The `TRACE` macro prints both the file name and a code indicating the reason for failure.  You can call the `AfxThrowFileException` function if you require more detailed error reporting.  
  
## 참고 항목  
 [CFile Class](../mfc/reference/cfile-class.md)   
 [CFile::Open](../Topic/CFile::Open.md)   
 [파일](../mfc/files-in-mfc.md)