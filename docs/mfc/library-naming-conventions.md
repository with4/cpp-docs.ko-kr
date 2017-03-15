---
title: "라이브러리 명명 규칙 | Microsoft Docs"
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
  - "코딩 규칙, MFC 라이브러리 이름"
  - "콘솔 응용 프로그램, MFC 라이브러리 버전"
  - "규칙[C++], MFC 라이브러리 이름"
  - "라이브러리[C++], static"
  - "MFC 라이브러리, 명명 규칙"
  - "NAFXCW.LIB"
  - "NAFXCWD.LIB"
  - "명명 규칙[C++], MFC 개체 코드 라이브러리"
  - "개체 코드 라이브러리"
  - "개체 코드 라이브러리, MFC 명명 규칙"
ms.assetid: 39fe7d93-5a14-4c6a-b16c-bf318fa01278
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 라이브러리 명명 규칙
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Object\-code libraries for MFC use the following naming conventions.  The library names have the form  
  
 *u*AFX`c`W`d`.LIB  
  
 where the letters shown in italic lowercase are placeholders for specifiers whose meanings are shown in the following table:  
  
### Library Naming Conventions  
  
|지정자|Values and meanings|  
|---------|-------------------------|  
|*u*|ANSI \(N\) or Unicode \(U\)|  
|`c`|Type of program to create: C\=all|  
|`d`|Debug or Release: D\=Debug; omit specifier for Release|  
  
 The default is to build a debug Windows ANSI application for the Intel platform: NAFXCWD.Lib.  All libraries listed in the following table are included prebuilt in the \\atlmfc\\lib directory on the Visual C\+\+ CD\-ROM.  
  
### Static\-Link Library Naming Conventions  
  
|라이브러리|설명|  
|-----------|--------|  
|NAFXCW.LIB|MFC Static\-Link Library, Release version|  
|NAFXCWD.LIB|MFC Static\-Link Library, Debug version|  
|UAFXCW.LIB|MFC Static\-Link Library with Unicode support, Release version|  
|UAFXCWD.LIB|MFC Static\-Link Library with Unicode support, Debug version|  
  
> [!NOTE]
>  If you need to build a library version, see the Readme.Txt file in the \\atlmfc\\src\\mfc directory.  This file describes using the supplied makefile with NMAKE.  
  
 For more information, see [Naming Conventions for MFC DLLs](../build/naming-conventions-for-mfc-dlls.md) and [Unicode Versions of the MFC Libraries](../mfc/unicode-in-mfc.md).  
  
## 참고 항목  
 [MFC 라이브러리 버전](../mfc/mfc-library-versions.md)