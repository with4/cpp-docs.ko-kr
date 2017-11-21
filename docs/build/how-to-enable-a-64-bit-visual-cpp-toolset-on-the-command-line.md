---
title: "방법: 명령줄에서 64 비트 Visual c + + 도구를 사용 하도록 설정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- x64 [C++]
- 64-bit compiler [C++], command line usage
- 64-bit compiler [C++], toolset enabling at command line
- command line [C++], 64-bit compiler
- Itanium [C++], command-line compiler
- IPF
- Itanium [C++]
- IPF, command-line compiler
- x64 [C++], command-line compiler
ms.assetid: 4da93a19-e20d-4778-902a-5eee9a6a90b5
caps.latest.revision: "30"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f776cbaec0b890959db180a373d4cb4152ac5826
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-enable-a-64-bit-x64-hosted-visual-c-toolset-on-the-command-line"></a>방법: 64 비트를 사용 하도록 설정, x64 호스트 명령줄에서 Visual c + + 도구 집합

Visual c + + 컴파일러, 링커 및 플랫폼 특정 버전의 32 비트, 64 비트 또는 ARM 기반 Windows 운영 체제에서 실행할 수 있는 응용 프로그램을 만드는 데 사용할 수 있는 다른 도구를 포함 합니다. Visual Studio의 기타 선택적 작업을 통해 c + + 도구를 사용 하 여 iOS, Android 및 Linux 등 다른 플랫폼을 대상으로 수 있습니다. 기본 빌드 아키텍처는 32 비트, x86 네이티브 Windows 코드를 빌드하려면 32 비트, x86 호스트 도구를 사용 합니다. 그러나 것 64 비트 컴퓨터를 보유 합니다. X86, x64 또는 ARM 프로세서에 대 한 코드를 빌드할 때 64 비트, x64 호스트 도구 집합을 사용 하 여 프로세서 및 64 비트 코드에서 사용 가능한 메모리 공간을 걸릴 수 있습니다.
  
> [!NOTE]
>  각 Visual c + + 버전에 포함 되는 특정 도구에 대 한 정보를 참조 하십시오. [Visual c + + 도구 및 Visual Studio 버전의 기능](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)합니다.  
>   
>  64 비트 응용 프로그램을 만들려면 Visual Studio IDE를 사용 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 대상 64 비트 x64 Visual c + + 프로젝트 구성 플랫폼](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)합니다.  
  
Visual Studio 설치 관리자에서 작업 부하를 c + +를 설치할 때 항상 32 비트, x86 호스트, 네이티브 및 크로스 컴파일러 도구를 빌드하는 x86 및 x64 코드를 설치 합니다. 유니버설 Windows 플랫폼 작업을 포함 하는 경우 또한 ARM 코드를 빌드하려면 x86 호스트 크로스 컴파일러 도구를 설치 합니다. 64 비트 x64에 이러한 작업 부하를 설치 하면 프로세서를 하면도 64 비트 네이티브 가져오고 크로스 컴파일러 및 도구를 빌드 x86, x64, ARM 코드입니다. 32 비트 및 64 비트 도구는 동일한 코드를 생성 하지만 64 비트 도구 미리 컴파일된 헤더 기호 및 전체 프로그램 최적화에 대 한 더 많은 메모리를 지원 ([/GL](../build/reference/gl-whole-program-optimization.md) 및 [/LTCG](../build/reference/ltcg-link-time-code-generation.md)) 옵션입니다. 32 비트 도구를 사용 하는 경우 실행 메모리 한계에 도달 하는 경우 64 비트 도구를 시도 하십시오.  

## <a name="use-a-64-bit-hosted-developer-command-prompt-shortcut"></a>64 비트 호스트 된 개발자 명령 프롬프트 바로 가기를 사용 하 여
  
Visual Studio가 64 비트 Windows 운영 체제에 설치, 64 비트, x64 호스트 네이티브 및 크로스 컴파일러가 개발자를 위한 추가 명령 프롬프트 바로 가기를 사용할 수 있습니다. Windows 10에서 이러한 명령 프롬프트에 액세스 하려면는 **시작** 메뉴, 예를 들어 Visual Studio 버전에 대 한 폴더를 열고 **Visual Studio 2017**, x64 네이티브 또는 크로스 도구 중 하나를 선택 하 고 개발자 명령 프롬프트입니다. Windows 8에서 이러한 명령 프롬프트에 액세스 하려면는 **시작** 화면, 열린 **모든 앱**합니다. 설치 된 버전의 Visual Studio에 대 한 머리글 아래에서 열고는 **Visual Studio** 폴더 (Visual Studio의 이전 버전에서에 이름을 지정할 수 있습니다 **Visual Studio Tools**). 이전 버전의 Windows에서 선택 **시작**를 확장 하 고 **모든 프로그램**, 사용 중인 버전에 대 한 폴더 **Visual Studio** (및 이전 버전의 Visual Studio에서  **Visual Studio Tools**). 자세한 내용은 참조 [개발자 명령 프롬프트 바로 가기](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)합니다.  
  
## <a name="use-vcvarsallbat-to-set-a-64-bit-hosted-build-architecture"></a>Vcvarsall.bat를 사용 하 여 호스팅된 빌드 64 비트 아키텍처를 설정 합니다.
  
파일을 명령 네이티브 또는 크로스 컴파일러 도구는 vcvarsall.bat를 실행 하 여 명령줄에서 빌드 구성을 사용할 수 있습니다. 이 명령 파일의 경로 구성 하 고 있는 특정 환경 변수는 기존 명령 프롬프트 창에는 아키텍처 빌드. 구체적인 지침은 참조 [개발자 명령 파일 및 위치](../build/building-on-the-command-line.md#developer_command_files) 합니다.  
  
## <a name="see-also"></a>참고 항목  

[64 비트 x64 Visual c + + 구성 대상](../build/configuring-programs-for-64-bit-visual-cpp.md)