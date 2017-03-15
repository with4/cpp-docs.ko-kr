---
title: "Visual C++에서 MBCS 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mbcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "아시아 언어[C++]"
  - "문자 집합[C++], 멀티바이트"
  - "중국어 문자[C++]"
  - "코드 편집기[C++], MBCS 지원"
  - "디버거[C++], MBCS 지원"
  - "더블바이트 문자 집합[C++]"
  - "IME[C++]"
  - "IME[C++], MBCS"
  - "Input Method Editor[C++]"
  - "Input Method Editor[C++], MBCS"
  - "일본어 문자[C++]"
  - "간지 문자 지원[C++]"
  - "MBCS[C++], 사용"
  - "멀티바이트 문자[C++]"
  - "NMAKE 프로그램, MBCS 지원"
  - "리소스 편집기[C++], MBCS 지원"
  - "도구[C++], MBCS 지원"
ms.assetid: 6179f6b7-bc61-4a48-9267-fb7951223e38
caps.latest.revision: 7
caps.handback.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Visual C++에서 MBCS 지원
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MBCS를 사용할 수 있는 버전의 Windows 2000 또는 Windows XP 운영 체제에서 Visual C\+\+ 개발 시스템을 실행하면 통합 소스 코드 편집기, 디버거, 명령줄 도구를 비롯한 모든 기능에서 MBCS가 지원되지만, 메모리 창은 예외입니다.  
  
 The memory window does not interpret bytes of data as MBCS characters, even though it can interpret them as ANSI or Unicode characters.  ANSI characters are always 1 byte in size and Unicode characters are 2 bytes in size.  With MBCS, characters can be 1 or 2 bytes in size and their interpretation depends on which code page is in use.  Because of this, it is difficult for the memory window to reliably display MBCS characters.  The memory window cannot know which byte is the start of a character.  개발자는 메모리 창에서 바이트 값을 보고 표에서 이 값을 조회하여 문자 표현을 확인할 수 있습니다.  개발자는 소스 코드를 기반으로 문자열의 시작 주소를 알 수 있기 때문입니다.  
  
 Visual C\+\+에서는 필요한 경우 언제나 더블바이트 문자를 사용할 수 있습니다.  여기에는 대화 상자의 경로 이름과 파일 이름 및 Visual C\+\+ 리소스 편집기의 텍스트 엔트리\(예: 대화 편집기의 정적 텍스트, 아이콘 편집기의 정적 텍스트 엔트리 등\)가 포함됩니다.  또한 전처리기는 일부 더블바이트 지시문\(예: `#include` 문의 파일 이름, **code\_seg**와 **data\_seg** pragma에 대한 인수 등\)을 인식합니다.  소스 코드 편집기에서 주석과 문자열 리터럴에 더블바이트 문자를 사용할 수 있습니다. 단, 변수 이름 같은 C\/C\+\+ 언어 요소에는 사용할 수 없습니다.  
  
##  <a name="_core_support_for_the_input_method_editor_.28.ime.29"></a> IME 지원  
 MBCS를 사용하는 일본 등의 동아시아 시장을 대상으로 작성된 응용 프로그램은 대개 싱글바이트와 더블바이트 문자를 모두 입력할 수 있는 Windows IME를 지원합니다.  Visual C\+\+ 개발 환경에는 IME에 대한 완전한 지원이 포함되어 있습니다.  자세한 내용은 [IME 샘플: IME 모드 제어 및 IME 수준 3 구현 방법 설명](http://msdn.microsoft.com/ko-kr/87ebdf65-cef0-451d-a6fc-d5fb64178b14)을 참조하십시오.  
  
 일본어 키보드는 간지 문자를 직접 지원하지 않습니다.  IME는 다른 일본어 문자인 로마지, 가타카나 또는 히라가나 중 하나로 입력된 음성 문자열을 가능한 간지 표현으로 변환합니다.  발음이 모호하면 몇 가지 대안 중에서 선택할 수 있습니다.  사용할 간지 문자를 선택하면 IME가 두 개의 `WM_CHAR` 메시지를 제어 응용 프로그램에 전달합니다.  
  
 Alt\+\` 키 조합으로 활성화되는 IME는 단추\(표시기\)와 변환 창으로 나타납니다.  응용 프로그램은 창을 텍스트 삽입 지점에 배치하며  변환 창을 대상 창의 새 위치나 크기에 따라 다시 배치함으로써 `WM_MOVE`와 `WM_SIZE` 메시지를 처리해야 합니다.  
  
 응용 프로그램 사용자가 간지 문자를 입력할 수 있도록 하려면 응용 프로그램에서 Windows IME 메시지를 처리해야 합니다.  IME 프로그래밍에 대한 자세한 내용은 [Input Method Editor](https://msdn.microsoft.com/en-us/library/ms776145.aspx)를 참조하십시오.  
  
## Visual C\+\+ 디버거  
 Visual C\+\+ 디버거는 IME 메시지에 중단점을 설정하는 기능을 제공합니다.  또한 메모리 창에는 더블바이트 문자를 표시할 수 있습니다.  
  
## 명령줄 도구  
 컴파일러, NMAKE 및 리소스 컴파일러\(RC.EXE\)를 비롯한 Visual C\+\+ 명령줄 도구는 MBCS를 지원합니다.  리소스 컴파일러의 \/c 옵션을 사용하면 응용 프로그램의 리소스를 컴파일할 때 기본 코드 페이지를 변경할 수 있습니다.  
  
 소스 코드를 컴파일할 때 기본 로캘을 변경하려면 [\#pragma setlocale](../preprocessor/setlocale.md)을 사용합니다.  
  
## 그래픽 도구  
 Spy\+\+, 리소스 편집 도구 등의 Visual C\+\+ Windows 기반 도구는 IME 문자열을 전적으로 지원합니다.  
  
## 참고 항목  
 [MBCS\(멀티바이트 문자 집합\) 지원](../text/support-for-multibyte-character-sets-mbcss.md)   
 [MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)