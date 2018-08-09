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
ms.openlocfilehash: 1d00495f95b3c67e4a6fc3613b949b8ae2946bd6
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010388"
---
# <a name="mbcs-support-in-visual-c"></a>Visual C++에서 MBCS 지원
MBCS 지원 버전의 Windows 실행 하는 경우 Visual c + + 개발 시스템 (통합된 소스 코드 편집기, 디버거 및 명령줄 도구 등)는 MBCS 지원, 메모리 창을 제외 하 고.  
  
 메모리 창 해석 하지는 않습니다 데이터의 바이트, MBCS 문자로 ANSI 또는 유니코드 문자로 해석할 수 있는 경우에 합니다. ANSI 문자는 항상 1 바이트 크기 및 유니코드 문자는 2 바이트 크기입니다. MBCS를 사용 하 여 문자 크기가 1 또는 2 바이트 수 및에 대 한 해석은 사용 하에서는 코드 페이지에 따라 달라 집니다. 이 인해 MBCS 문자를 안정적으로 표시할 메모리 창에 대 한 어렵습니다. 메모리 창에는 선행 바이트 문자를 알 수 없습니다. 개발자는 메모리 창에 바이트 값을 보고 하 고 문자 표현을 결정 하는 테이블의 값을 조회 수 있습니다. 개발자는 소스 코드를 기반으로 하는 문자열의 시작 주소를 알고 있기 때문에 이것이 가능 합니다.  
  
 이렇게 하려면 필요한 경우 언제나 visual c + + 더블 바이트 문자를 허용 합니다. Visual c + + 리소스 편집기 (예: 대화 상자 편집기에서 정적 텍스트)와 아이콘 편집기에 정적 텍스트 항목에서에서 텍스트 항목 대화 상자에 경로 및 파일 이름을 포함 됩니다. 전처리기는 일부 더블 바이트 지시문을 인식 하는 또한-예를 들어 파일의 이름을 `#include` 문 및에 대 한 인수로 합니다 `code_seg` 및 `data_seg` pragma입니다. 소스 코드 편집기에서 더블 바이트 문자 문자열 리터럴 및 주석에서는 아니지만 (예: 변수 이름은) C/c + + 언어 요소가 허용 됩니다.  
  
##  <a name="_core_support_for_the_input_method_editor_.28.ime.29"></a> 지원에 대 한 입력 방법 편집기를 IME)  
 일반적으로 (예를 들어 일본) MBCS를 사용 하는 동아시아 시장 및 더블 바이트 문자를 모두 입력에 대 한 Windows IME 지원 용으로 작성 된 응용 프로그램입니다. Visual c + + 개발 환경에는 IME에 대 한 전체 지원을 포함합니다. 자세한 내용은 [IME 샘플: 컨트롤의 IME 모드 및 IME 수준 3 구현 방법 설명](http://msdn.microsoft.com/87ebdf65-cef0-451d-a6fc-d5fb64178b14)합니다.  
  
 일본어 키보드 간지 문자를 직접 지원 하지 않습니다. IME 간지 표현 가능한에 다른 일본어 (로마지, 가타카나, 또는 히라가나) 중 하나에서 입력 음성 문자열을 변환 합니다. 모호성 인 경우에 여러 가지 대안 중에서 선택할 수 있습니다. IME 간지 문자를 선택한 경우 두 전달 `WM_CHAR` 제어 응용 프로그램에는 메시지입니다.  
  
 ALT + 활성화 IME를\` 키 조합을, 단추 (표시기) 집합과 변환 창으로 표시 됩니다. 응용 프로그램 창을 텍스트 삽입 지점에 배치합니다. 응용 프로그램 처리 해야 합니다 `WM_MOVE` 고 `WM_SIZE` 새 위치 또는 대상 창의 크기에 맞게 변환 창을 기준으로 메시지입니다.  
  
 간지 문자를 입력할 수 있도록 응용 프로그램의 사용자를 하려는 경우 응용 프로그램 Windows IME 메시지를 처리 해야 합니다. IME 프로그래밍에 대 한 자세한 내용은 참조 하세요. [Input Method Editor](https://msdn.microsoft.com/library/ms776145.aspx)합니다.  
  
## <a name="visual-c-debugger"></a>Visual c + + 디버거  
 Visual c + + 디버거는 IME 메시지에 중단점을 설정 하는 기능을 제공 합니다. 또한 메모리 창을 더블 바이트 문자를 표시할 수 있습니다.  
  
## <a name="command-line-tools"></a>명령줄 도구  
 컴파일러, NMAKE, 리소스 컴파일러 (RC 등 Visual c + + 명령줄 도구. EXE), MBCS를 사용 하도록 설정 합니다. 응용 프로그램의 리소스를 컴파일하는 경우 기본 코드 페이지를 변경 하려면 리소스 컴파일러의 /c 옵션을 사용할 수 있습니다.  
  
 소스 코드 컴파일 타임에 기본 로캘을 변경 하려면 [#pragma setlocale](../preprocessor/setlocale.md)합니다.  
  
## <a name="graphical-tools"></a>그래픽 도구  
 Spy + + 및 편집 도구, 리소스와 같은 Visual c + + Windows 기반 도구는 완벽 하 게 IME 문자열을 지원 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [멀티 바이트 문자 집합 (Mbcs)에 대 한 지원](../text/support-for-multibyte-character-sets-mbcss.md)   
 [MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)