---
title: "링커 입력 파일로 사용하는 .Obj 파일 | Microsoft Docs"
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
  - "링커 입력 파일로 사용하는 .obj 파일"
  - "COFF 파일"
  - "LINK 도구[C++], .obj 파일"
  - "링커[C++], 입력으로 사용하는 OBJ 파일"
  - "링커 입력으로 사용하는 OBJ 파일"
  - "개체 파일, 링커 출력"
  - "OMF 개체 파일"
ms.assetid: 3028e423-8b10-4972-8eb4-6e9ae58f0a26
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 입력 파일로 사용하는 .Obj 파일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

링커 도구\(LINK.EXE\)는 COFF\(공용 개체 파일 형식\)인 .obj 파일을 사용합니다.  
  
## 설명  
 Microsoft는 공용 개체 파일 형식을 정의하는 다운로드 가능 문서를 제공합니다.  자세한 내용을 보려면 [Microsoft Portable Executable and Common Object File Format Specification](http://go.microsoft.com/fwlink/?LinkId=93292) 8.1 및 이후 버전을 다운로드하십시오.  
  
## 유니코드 지원  
 Visual Studio 2005부터는 Microsoft Visual C\+\+ 컴파일러에서 ISO\/IEC C 및 C\+\+ 표준에 정의된 대로 식별자의 유니코드 문자를 지원합니다.  이전 버전의 컴파일러에서는 식별자에서 ASCII 문자만 지원했습니다.  함수, 클래스 및 정적 이름에서 유니코드를 지원하기 위해 컴파일러와 링커는 .obj 파일의 COFF 기호에 대해 유니코드 UTF\-8 인코딩을 사용합니다.  UTF\-8 인코딩은 Visual Studio 이전 버전에서 사용된 ASCII 인코딩과 호환됩니다.  
  
 컴파일러 및 링커에 대한 자세한 내용은 [컴파일러 및 링커에서의 유니코드 지원](../../build/reference/unicode-support-in-the-compiler-and-linker.md)을 참조하십시오.  유니코드 표준에 대 한 자세한 내용은 참조는 [유니코드](http://go.microsoft.com/fwlink/?LinkId=37123) 조직을 확인하세요.  
  
## 참고 항목  
 [LINK 입력 파일](../../build/reference/link-input-files.md)   
 [링커 옵션](../../build/reference/linker-options.md)   
 [유니코드 지원](../../text/support-for-unicode.md)   
 [컴파일러 및 링커에서의 유니코드 지원](../../build/reference/unicode-support-in-the-compiler-and-linker.md)   
 [유니코드 표준은](http://go.microsoft.com/fwlink/?LinkId=37123)   
 [공용 개체 파일 형식 사양](http://go.microsoft.com/fwlink/?LinkId=93292)