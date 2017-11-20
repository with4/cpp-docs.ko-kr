---
title: "유니코드에 대 한 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- globalization [C++], character sets
- portable data types [MFC]
- Unicode [C++]
- wide characters [C++], about wide characters
- character sets [C++], Unicode
- localization [C++], character sets
- Unicode [C++], installing support
ms.assetid: 180f1d10-8543-4f79-85ce-293d3cb443bb
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: b58901f213d5e69eb50ad449a87266736fba0af7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="support-for-unicode"></a>유니코드 지원
유니코드는 1바이트로 표현할 수 없는 문자를 비롯하여 모든 문자 집합을 지원하는 사양입니다. 국제 시장을 프로그래밍 하는 경우 유니코드를 사용 하는 것이 좋습니다 또는 [멀티 바이트 문자 집합](../text/support-for-multibyte-character-sets-mbcss.md) (Mbcs) 사용 하거나 스위치 변경을 통해 빌드할 수 있도록 프로그램을 사용 합니다.  
  
 와이드 문자는 2바이트 다국어 문자 코드입니다. 기술 기호 및 특수 게시 문자를 비롯하여 전 세계 첨단 컴퓨팅에 사용되는 대부분의 문자는 유니코드 사양에 따라 와이드 문자로 표현할 수 있습니다. 와이드 문자 하나로 표현할 수 없는 문자는 유니코드 서로게이트 기능을 사용하여 유니코드 쌍으로 표현할 수 있습니다. 모든 와이드 문자는 16비트의 고정 크기로 표현되므로 와이드 문자를 사용하면 국제 문자 집합을 사용한 프로그래밍이 간소화됩니다.  
  
 와이드 문자열은으로 표시 됩니다는 **wchar_t** 배열 하 고 2를 가리키고는 `wchar_t*` 포인터입니다. 모든 ASCII 문자는 문자 앞에 접두사로 문자 L을 붙여 와이드 문자로 표현할 수 있습니다. 예를 들어 L'\ \0'은 종결 와이드 (16 비트) **NULL** 문자입니다. 마찬가지로, ASCII 문자열 리터럴은 ASCII 리터럴에 접두사로 문자 L을 붙여(예: L"Hello") 와이드 문자열 리터럴로 표현할 수 있습니다.  
  
 일반적으로 와이드 문자는 멀티바이트 문자보다 더 많은 메모리 공간을 차지하지만 프로세스 속도는 더 빠릅니다. 또한 멀티바이트 인코딩 시 1개 로캘만 표현할 수 있지만 전 세계 모든 문자 집합은 유니코드 표현으로 동시에 표현할 수 있습니다.  
  
 MFC 프레임워크 전체에서는 유니코드를 사용할 수 있으며 MFC에서는 다음 테이블에 표시된 것처럼 이식 가능한 매크로를 사용하여 유니코드를 사용할 수 있습니다.  
  
### <a name="portable-data-types-in-mfc"></a>MFC의 이식 가능한 데이터 형식  
  
|이식 불가능한 데이터 형식|다음 매크로로 바뀜|  
|-----------------------------|----------------------------|  
|`char`|_**TCHAR**|  
|**char\***, **LPSTR (Win32 데이터 형식)**|`LPTSTR`|  
|**const char\*, LPCSTR (Win32 데이터 형식)**|`LPCTSTR`|  
  
 클래스 `CString` 사용 하 여 **_TCHAR** 의 기반으로 하 고 쉬운 변환을 위해 생성자 및 연산자를 제공 합니다. 유니코드에 대한 대부분의 문자열 작업은 Windows ANSI 문자 집합을 처리하는 데 사용되는 것과 동일한 논리를 사용하여 작성할 수 있습니다. 이러한 논리는 작업의 기본 단위가 8비트 바이트 대신 16비트 문자라는 점이 다릅니다. 멀티바이트 문자 집합을 사용하는 것과 달리 유니코드 문자를 별도의 2바이트인 것처럼 처리할 필요가 없습니다.  
  
## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
-   [MFC 통해 유니코드 지원 설치](../mfc/unicode-in-mfc.md)  
  
-   [프로그램에서 유니코드 사용](../text/international-enabling.md)  
  
-   [유니코드와 MBCS 프로그램에서 사용](../text/internationalization-strategies.md)  
  
-   [유니코드를 사용 하 여 국제화 된 프로그램 만들기](../text/unicode-programming-summary.md)  
  
-   [어떻게 유니코드를 사용 하는 프로그램의 보다 효율적인 Windows 2000에서 비롯 한 유니코드의 이점에 알아보기](../text/benefits-of-character-set-portability.md)  
  
-   [와이드 문자 인수를 프로그램에 전달할 수 있도록 wmain 사용](../text/support-for-using-wmain.md)  
  
-   [유니코드 프로그래밍 요약 참조](../text/unicode-programming-summary.md)  
  
-   [바이트 너비 이식성에 대 한 제네릭 텍스트 매핑에 대 한 자세한 내용은](../text/generic-text-mappings-in-tchar-h.md)  
  
## <a name="see-also"></a>참고 항목  
 [텍스트 및 문자열](../text/text-and-strings-in-visual-cpp.md)   
 [wmain 사용 지원](../text/support-for-using-wmain.md)