---
title: "국제화 전략 | Microsoft Docs"
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
  - "문자 집합[C++], 국가별 프로그래밍 전략"
  - "전역화[C++], 문자 집합"
  - "언어를 이식할 수 있는 코드[C++]"
  - "지역화[C++], 문자 집합"
  - "MBCS[C++], 국제화 전략"
  - "유니코드[C++], 응용 프로그램 전역화"
  - "Win32[C++], 국가별 프로그래밍 전략"
  - "Windows API[C++], 국가별 프로그래밍 전략"
ms.assetid: b09d9854-0709-4b9a-a00c-b0b8bc4199b1
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# 국제화 전략
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대상 운영 체제와 시장에 따라 다음 몇 가지 국제화 전략을 사용할 수 있습니다.  
  
-   응용 프로그램에서 유니코드를 사용하여 Windows 2000 및 Windows NT에서 실행되지만 Windows 95 또는 Windows 98에서는 실행되지 않습니다.  
  
     사용자는 유니코드 관련 추가 기능을 사용하며 모든 문자는 16비트입니다. 그러나 특별한 용도로 프로그램의 일부분에서 ANSI 문자를 사용할 수도 있습니다.  C 런타임 라이브러리는 유니코드 전용 프로그래밍을 위해 함수, 매크로 및 데이터 형식을 제공합니다.  MFC는 유니코드를 완벽하게 지원합니다.  
  
-   응용 프로그램이 MBCS를 사용하며 모든 Win32 플랫폼에서 실행할 수 있습니다.  
  
     사용자는 MBCS 관련 추가 기능을 사용합니다.  문자열에는 싱글바이트 문자, 더블바이트 문자 또는 둘 다 포함될 수 있습니다.  C 런타임 라이브러리는 MBCS 전용 프로그래밍을 위해 함수, 매크로 및 데이터 형식을 제공합니다.  MFC는 MBCS를 완벽하게 지원합니다.  
  
-   응용 프로그램의 소스 코드가 완전한 이식성을 제공하도록 작성되었습니다. 정의된 **\_UNICODE** 기호나 **\_MBCS** 기호를 사용하여 다시 컴파일하면 둘 중 하나를 사용하는 버전을 만들 수 있습니다.  자세한 내용은 [Tchar.h의 제네릭 텍스트 매핑](../text/generic-text-mappings-in-tchar-h.md)을 참조하십시오.  
  
-   Your application uses a wrapper library for missing Unicode functions on Windows 95, Windows 98, and Windows ME like the one described in [Design a Single Unicode App that Runs on Both Windows 98 and Windows 2000](http://go.microsoft.com/fwlink/p/?LinkId=250770).  래퍼 라이브러리는 상업적으로도 제공됩니다.  
  
     사용자는 완전히 이식 가능한 C 런타임 함수, 매크로 및 데이터 형식을 사용합니다.  MFC에는 유연성이 있어서 이러한 전략을 모두 지원합니다.  
  
 나머지 항목에서는 유니코드나 MBCS로 빌드할 수 있는 완전히 이식 가능한 코드 작성에 대해 중점적으로 다룹니다.  
  
## 참고 항목  
 [유니코드 및 MBCS](../text/unicode-and-mbcs.md)   
 [로캘 및 코드 페이지](../text/locales-and-code-pages.md)