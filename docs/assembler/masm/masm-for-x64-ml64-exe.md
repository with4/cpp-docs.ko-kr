---
title: MASM (ml64.exe) x64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ml64
- ml64.exe
- masm for x64
ms.assetid: 89059103-f372-4968-80ea-0c7f90bb9c91
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a42b25b5d86d181bed907a3b437d28f3cbf5e820
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="masm-for-x64-ml64exe"></a>x64용 MASM (ml64.exe)

Visual Studio는 32 비트 및 64 비트 호스트 된 버전의 MASM x64 대상 코드에 포함 되어 있습니다. X64 허용 하는 어셈블러는 ml64.exe 명명 된, 어셈블러 언어입니다. MASM 명령줄 도구는 Visual Studio를 설치 하는 동안 c + + 작업을 선택 하면 설치 됩니다. 이러한 도구는 별도 다운로드로 사용할 수 없습니다. 참조를 다운로드 하 고 Visual Studio의 복사본을 설치할 [https://www.visualstudio.com/](https://www.visualstudio.com/)합니다. Visual Studio IDE를 설치 하지 않을 않고 원하는 명령줄 도구를 경우 참조는 **Visual Studio 2017 용 빌드 도구** 옵션에 [Visual Studio 다운로드](https://www.visualstudio.com/downloads/) 페이지.

작성 하는 MASM을 사용 하려면 x64에 대 한 코드를 명령줄에서 대상으로 x64 개발자 명령 프롬프트를 사용 해야 합니다 필요한 경로 및 다른 환경 변수를 설정 하는 대상입니다. 개발자 명령 프롬프트를 시작 하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드 C/c + + 코드](../../build/building-on-the-command-line.md)합니다.

Ml64.exe 명령줄 옵션에 대 한 자세한 내용은 참조 하십시오. [ML 및 ML64 명령줄 참조](../../assembler/masm/ml-and-ml64-command-line-reference.md)합니다.  
  
인라인 어셈블러 또는 ASM 키워드를 사용할 경우 x64 또는 ARM 대상에 대 한 지원 되지 않습니다. 이식 하 여 x86 코드를 사용 하 여 인라인 어셈블러 x64 또는 ARM을 c + + 코드를 변환, 컴파일러 내장 함수를 사용 하거나 만들 수 있습니다 어셈블러 언어 소스 파일. Visual c + + 컴파일러는 내장 함수 예제에서는 한 권한이 검색/테스트, 연관, 등에에서으로 플랫폼 간 방식으로 최대한 가깝게 비트에 대 한 특수 함수 지침을 사용할 수 있도록 지원 합니다. 사용할 수 있는 내장 함수에 대 한 자세한 내용은 참조 [컴파일러 내장](../../intrinsics/compiler-intrinsics.md)합니다.  

## <a name="add-an-assembler-language-file-to-a-visual-c-project"></a>Visual c + + 프로젝트에 어셈블러 언어 파일을 추가 합니다.  
  
Visual Studio 프로젝트 시스템 MASM c + + 프로젝트에서 사용 하 여 작성 된 어셈블러 언어 파일을 지원 합니다. X64 어셈블러 언어 소스 파일을 완전히 x64를 지 원하는 MASM을 사용 하 여 개체 파일에 빌드를 만들 수 있습니다. 이러한 개체 파일 x64 용으로 작성 된 c + + 코드에 링크할 수 있습니다 대상으로 합니다. 이 한 가지 방법은 x64 부족을 해결 하기 위해 인라인 어셈블러 합니다.  

### <a name="to-add-an-assembler-language-file-to-an-existing-visual-c-project"></a>기존 Visual c + + 프로젝트에 어셈블러 언어 파일을 추가 하려면

1. 프로젝트를 선택 **솔루션 탐색기**합니다. 메뉴 모음에서 **프로젝트**, **빌드 사용자 지정**합니다.

1. 에 **Visual c + + 빌드 사용자 지정 파일** 대화 상자에서 옆에 확인란 **masm(.targets,.props)**합니다. 선택 **확인** 하 여 선택 내용을 저장 하 고 대화 상자를 닫습니다.

1. 메뉴 모음에서 **프로젝트**, **새 항목 추가**합니다. 

1. 에 **새 항목 추가** 대화 상자에서 **c + + 파일 (.cpp)** 가운데 창에서. 에 **이름** 편집 컨트롤을 가진 새 파일 이름을 입력 한 **.asm** .cpp 대신 확장명입니다. 선택 **추가** 하는 파일을 프로젝트에 추가 하 고 대화 상자를 닫습니다.

추가한.asm 파일에 어셈블러 언어 코드를 만듭니다. 솔루션을 빌드할 때 프로젝트에 다음 연결 된 개체 파일에.asm 파일 어셈블하기 MASM 어셈블러 호출 됩니다. 기호 액세스를 간단 하 게 하려면으로 어셈블러 함수를 선언 `extern "C"` c + + 소스 코드에서 c + +를 사용 하는 대신 어셈블러-언어로 장식 규칙이 소스 파일 이름입니다.
  
## <a name="ml64-specific-directives"></a>ml64 별 지시문  

어셈블러 언어 소스 코드를 x64 대상에 다음 ml64 별 지시문을 사용할 수 있습니다.  
  
-   [.ALLOCSTACK](../../assembler/masm/dot-allocstack.md)  
  
-   [.ENDPROLOG](../../assembler/masm/dot-endprolog.md)  
  
-   [.PUSHFRAME](../../assembler/masm/dot-pushframe.md)  
  
-   [.PUSHREG](../../assembler/masm/dot-pushreg.md)  
  
-   [.SAVEREG](../../assembler/masm/dot-savereg.md)  
  
-   [.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)  
  
-   [.SETFRAME](../../assembler/masm/dot-setframe.md)  
  
또한는 [PROC](../../assembler/masm/proc.md) 지시문 ml64.exe 사용 하도록 업데이트 되었습니다.  
  
## <a name="32-bit-address-mode-address-size-override"></a>32 비트 주소 모드 (주소 크기 재정의)  

MASM은 메모리 피연산자에 32 비트 레지스터에 포함 된 경우 0x67 주소 크기 재정을 내보냅니다. 예를 들어 다음 예제에서는 주소 크기 재정의를 생성할 수 발생 합니다.  
  
```MASM  
mov rax, QWORD PTR [ecx]  
mov eax, DWORD PTR [ecx*2+r10d]  
mov eax, DWORD PTR [ecx*2+r10d+0100h]  
prefetch [eax]  
movnti rax, QWORD PTR [r8d]  
```  
  
MASM는 32 비트 치환 메모리 피연산자로 단독으로 나타나는, 64 비트 주소 지정 하려는 경우를 가정 합니다. 현재 이러한 피연산자와 함께 32 비트 주소 지정에 대 한 지원 되지 않습니다 됩니다.  
  
마지막으로, 다음 코드와 같이 메모리 피연산자 내 레지스터 크기를 혼합 하면 오류가 발생 합니다.  
  
```MASM  
mov eax, DWORD PTR [rcx*2+r10d]  
mov eax, DWORD PTR [ecx*2+r10+0100h]  
```  
  
## <a name="see-also"></a>참고 항목  

[Microsoft 매크로 어셈블러 참조](../../assembler/masm/microsoft-macro-assembler-reference.md)