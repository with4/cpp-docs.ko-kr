---
title: Visual c + +에서 MBCS 지원 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- _mbcs
dev_langs:
- C++
helpviewer_keywords:
- tools [C++], MBCS support
- Asian languages [C++]
- Code Editor [C++], MBCS support
- IME [C++]
- Chinese characters [C++]
- Input Method Editor [C++], MBCS
- resource editors [C++], MBCS support
- debugger [C++], MBCS support
- character sets [C++], multibyte
- Japanese characters [C++]
- multibyte characters [C++]
- Kanji character support [C++]
- NMAKE program, MBCS support
- double-byte character sets [C++]
- IME [C++], MBCS
- Input Method Editor [C++]
- MBCS [C++], enabling
ms.assetid: 6179f6b7-bc61-4a48-9267-fb7951223e38
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 41d075edb01fc139660d8e72a7fe53f03ee9e80b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="mbcs-support-in-visual-c"></a>Visual C++에서 MBCS 지원
MBCS 지원 버전의 Windows 실행 하는 경우 Visual c + + 개발 시스템 등 통합된 소스 코드 편집기, 디버거 및 명령줄 도구는 MBCS 지원, 메모리 창 제외 하 고.  
  
 메모리 창 해석 하지는 않습니다 데이터의 바이트 MBCS 문자로 ANSI 또는 유니코드 문자로 해석할 수 있는 경우에 합니다. ANSI 문자는 항상 1 바이트의 크기 및 유니코드 문자는 2 바이트의 크기입니다. Mbcs, 문자 크기가 1 또는 2 바이트를 사용할 수 있습니다 및의 해석을 사용 하에서는 코드 페이지에 따라 달라 집니다. 이 때문에 안정적으로 MBCS 문자가 표시 메모리 창에 대 한 어렵습니다. 메모리 창은 선행 바이트의 문자를 알 수 없습니다. 개발자는 메모리 창에 바이트 값을 볼 수 있으며 문자 표시를 확인 하는 테이블의 값을 조회 됩니다. 개발자는 소스 코드를 기반으로 문자열의 시작 주소를 알고 때문에 이것이 가능 합니다.  
  
 이렇게 하려면 적절 한 경우 언제 든 지 visual c + + 더블 바이트 문자를 허용 합니다. 이 경로 이름 및 파일 이름 대화 상자와 아이콘 편집기에서 정적 텍스트 항목 (예를 들어 대화 상자 편집기에서 정적 텍스트) 및 Visual c + + 리소스 편집기에서 텍스트 항목에 포함합니다. 전처리기 일부 더블 바이트 지시문을 인식 하는 또한-예를 들어 파일 이름 `#include` 문, 및의 인수로 서의 **code_seg** 및 **data_seg** pragma입니다. 소스 코드 편집기에서 주석 및 리터럴 문자열에 더블 바이트 문자에 없는 (예: 변수 이름은) C/c + + 언어 요소가 허용 됩니다.  
  
##  <a name="_core_support_for_the_input_method_editor_.28.ime.29"></a> 지원에 대 한는 입력 (입력기)  
 일반적으로 (예: 일본) MBCS를 사용 하는 동아시아 지역/국가 및 더블 바이트 문자를 모두 입력 하기 위한 Windows IME 지원 용으로 작성 된 응용 프로그램입니다. Visual c + + 개발 환경 IME 수 있는 기능을 포함합니다. 자세한 내용은 참조 [IME 샘플: 컨트롤의 IME 모드 및 IME 수준 3 구현 방법 설명](http://msdn.microsoft.com/en-us/87ebdf65-cef0-451d-a6fc-d5fb64178b14)합니다.  
  
 일본어 키보드 간지 문자를 직접 지원 하지 않습니다. IME 간지 표현 가능한는 다른 일본어 (Romaji, 가타카나, 또는 히라가나) 중 하나에 입력 된 음성 문자열을 변환 합니다. 모호성이 있으면 여러 대체에서 선택할 수 있습니다. IME 간지 문자를 선택한 경우 두 개의 전달 `WM_CHAR` 제어 응용 프로그램 메시지입니다.  
  
 ALT +에 의해 활성화 IME\` 키 조합을는 단추 (표시기)와 변환 창으로 나타납니다. 응용 프로그램 창을 텍스트 삽입 지점에 배치합니다. 처리 해야 `WM_MOVE` 및 `WM_SIZE` 새 위치 또는 대상 창 크기에 맞게 변환 창을 여는 메시지입니다.  
  
 간지 문자를 입력 하는 기능을 응용 프로그램 사용자가 하려는 경우 응용 프로그램 Windows IME 메시지를 처리 해야 합니다. IME 프로그래밍에 대 한 자세한 내용은 참조 [입력 방법 편집기](https://msdn.microsoft.com/en-us/library/ms776145.aspx)합니다.  
  
## <a name="visual-c-debugger"></a>Visual c + + 디버거  
 Visual c + + 디버거는 IME 메시지에 중단점을 설정 하는 기능을 제공 합니다. 또한, 메모리 창 더블 바이트 문자를 표시할 수 있습니다.  
  
## <a name="command-line-tools"></a>명령줄 도구  
 Visual c + + 명령줄 도구는 컴파일러, NMAKE, 및 리소스 컴파일러 (RC 포함. EXE), MBCS를 사용 하도록 설정 합니다. 응용 프로그램의 리소스를 컴파일할 경우에 기본 코드 페이지를 변경 하려면 리소스 컴파일러의 /c 옵션을 사용할 수 있습니다.  
  
 기본 로캘을 소스 코드 컴파일 시간을 변경 하려면 사용 [#pragma setlocale](../preprocessor/setlocale.md)합니다.  
  
## <a name="graphical-tools"></a>그래픽 도구  
 Spy + + 및 편집 도구, 리소스와 같은 Visual c + + Windows 기반 도구 IME 문자열을 완전 하 게 지원 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [멀티 바이트 문자 집합 (Mbcs)에 대 한 지원](../text/support-for-multibyte-character-sets-mbcss.md)   
 [MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)