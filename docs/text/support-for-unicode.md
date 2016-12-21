---
title: "유니코드 지원 | Microsoft Docs"
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
  - "문자 집합[C++], Unicode"
  - "전역화[C++], 문자 집합"
  - "지역화[C++], 문자 집합"
  - "이식 가능한 데이터 형식[MFC]"
  - "유니코드[C++]"
  - "유니코드[C++], 지원 설치"
  - "와이드 문자[C++], 와이드 문자 정보"
ms.assetid: 180f1d10-8543-4f79-85ce-293d3cb443bb
caps.latest.revision: 10
caps.handback.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# 유니코드 지원
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

유니코드는 1바이트로 표현할 수 없는 문자를 비롯하여 모든 문자 집합을 지원하는 사양입니다.  해외 시장을 겨냥한 제품을 프로그래밍 중이면 유니코드 또는 MBCS\([멀티바이트 문자 집합](../text/support-for-multibyte-character-sets-mbcss.md)\)를 사용하거나 스위치 변경을 통해 프로그램을 빌드할 수 있도록 프로그램을 설정하는 것이 좋습니다.  
  
 와이드 문자는 2바이트 다국어 문자 코드입니다.  기술 기호 및 특수 게시 문자를 비롯하여 전 세계 첨단 컴퓨팅에 사용되는 대부분의 문자는 유니코드 사양에 따라 와이드 문자로 표현할 수 있습니다.  와이드 문자 하나로 표현할 수 없는 문자는 유니코드 서로게이트 기능을 사용하여 유니코드 쌍으로 표현할 수 있습니다.  모든 와이드 문자는 16비트의 고정 크기로 표현되므로 와이드 문자를 사용하면 국제 문자 집합을 사용한 프로그래밍이 간소화됩니다.  
  
 와이드 문자열은 **wchar\_t\[\]** 배열로 표현되고 `wchar_t*` 포인터로 가리킵니다.  모든 ASCII 문자는 문자 앞에 접두사로 문자 L을 붙여 와이드 문자로 표현할 수 있습니다.  예를 들어 L'\\0'은 종료 와이드\(16비트\) **NULL** 문자입니다.  마찬가지로, ASCII 문자열 리터럴은 ASCII 리터럴에 접두사로 문자 L을 붙여\(예: L"Hello"\) 와이드 문자열 리터럴로 표현할 수 있습니다.  
  
 일반적으로 와이드 문자는 멀티바이트 문자보다 더 많은 메모리 공간을 차지하지만 프로세스 속도는 더 빠릅니다.  또한 멀티바이트 인코딩 시 1개 로캘만 표현할 수 있지만 전 세계 모든 문자 집합은 유니코드 표현으로 동시에 표현할 수 있습니다.  
  
 MFC 프레임워크 전체에서는 유니코드를 사용할 수 있으며 MFC에서는 다음 테이블에 표시된 것처럼 이식 가능한 매크로를 사용하여 유니코드를 사용할 수 있습니다.  
  
### MFC의 이식 가능한 데이터 형식  
  
|이식 불가능한 데이터 형식|다음 매크로로 바뀜|  
|--------------------|----------------|  
|`char`|\_**TCHAR**|  
|**char\***, **LPSTR\(Win32 데이터 형식\)**|`LPTSTR`|  
|**const char\*, LPCSTR\(Win32 데이터 형식\)**|`LPCTSTR`|  
  
 `CString` 클래스는 기본 클래스로 **\_TCHAR**을 사용하고 쉬운 변환을 위해 생성자 및 연산자를 제공합니다.  유니코드에 대한 대부분의 문자열 작업은 Windows ANSI 문자 집합을 처리하는 데 사용되는 것과 동일한 논리를 사용하여 작성할 수 있습니다. 이러한 논리는 작업의 기본 단위가 8비트 바이트 대신 16비트 문자라는 점이 다릅니다.  멀티바이트 문자 집합을 사용하는 것과 달리 유니코드 문자를 별도의 2바이트인 것처럼 처리할 필요가 없습니다.  
  
## 수행할 작업  
  
-   [MFC를 통해 유니코드 지원 설치](../mfc/unicode-in-mfc.md)  
  
-   [프로그램에서 유니코드 사용](../text/international-enabling.md)  
  
-   [프로그램에서 유니코드 및 MBCS 둘 다 사용](../text/internationalization-strategies.md)  
  
-   [유니코드를 사용하여 국제화된 프로그램 만들기](../text/unicode-programming-summary.md)  
  
-   [Windows 2000에서 유니코드 사용으로 프로그램을 더욱 효율적으로 만드는 방법을 비롯한 유니코드의 이점에 대해 알아보기](../text/benefits-of-character-set-portability.md)  
  
-   [와이드 문자 인수를 프로그램에 전달할 수 있도록 wmain 사용](../text/support-for-using-wmain.md)  
  
-   [유니코드 프로그래밍 요약 참조](../text/unicode-programming-summary.md)  
  
-   [바이트 너비 이식성을 위한 제네릭 텍스트 매핑에 대해 알아보기](../text/generic-text-mappings-in-tchar-h.md)  
  
## 참고 항목  
 [텍스트 및 문자열](../text/text-and-strings-in-visual-cpp.md)   
 [wmain 사용 지원](../text/support-for-using-wmain.md)