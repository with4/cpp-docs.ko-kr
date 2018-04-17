---
title: C/c + + 빌드 참조 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- compiling source code [C++], additional information
- cl.exe compiler [C++], building programs
- linker [C++], building reference
- builds [C++], additional information
ms.assetid: 100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e2269be27dd039357c11d38a2be83b5fc9d6504
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cc-building-reference"></a>C/C++ 빌드 참조
Visual c + +에는 C/c + + 프로그램 빌드의 두 가지 방법을 제공 합니다. 가장 쉬운 하 고 가장 일반적인 방법은 [Visual c + + 개발 환경 내에서 빌드](../../ide/building-cpp-projects-in-visual-studio.md)합니다. 다른 방법은 [명령줄 도구를 사용 하 여 명령 프롬프트에서 빌드](../../build/building-on-the-command-line.md)합니다. 두 경우 모두 Visual c + + 소스 편집기 또는 사용자가 선택한 제 3 자 편집기를 사용 하 여 소스 파일을 만들 수 있습니다.  
  
 프로그램이.vcxproj 파일 보다는 메이크파일의 사용 하는 경우 빌드할 수 있습니다 것으로 개발 환경에서 프로그램 [외부 프로젝트](../../ide/building-external-projects.md)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [ 프로그램 컴파일](../../build/reference/compiling-a-c-cpp-program.md)  
 기계어 코드, 링커 지시문, 섹션, 외부 참조 및 이름은 함수/데이터를 포함 하는 개체 파일을 만드는 컴파일러에 설명 합니다.  
  
 [링크](../../build/reference/linking.md)  
 정적으로 연결 된 라이브러리 및 컴파일러에서 생성 된 개체 파일에서 코드를 결합 하는 링커 설명 이름 참조를 해결 하 고 실행 파일을 만듭니다.  
  
 [릴리스 빌드](../../build/reference/release-builds.md)  
 디버그를으로 변경 하려면는 이유 및 시기에 한 정보를 제공 릴리스 빌드를 빌드하고 릴리스 빌드로 디버그에서 변경할 때 발생할 수 문제 중 일부에 대해서도 설명 합니다.  
  
 [코드 최적화](../../build/reference/optimizing-your-code.md)  
 코드를 최적화 하기 위한 메커니즘을 설명 하는 항목에 대 한 링크를 제공 합니다.  
  
 [ 빌드 도구](../../build/reference/c-cpp-build-tools.md)  
 보거나 빌드 출력을 조작 하기 위한 다음과 같은 명령줄 도구를 제공 합니다.  
  
 [C++ 빌드 오류](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)  
 내용의 테이블의 빌드 오류 섹션을 소개합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [ 전처리기 참조](../../preprocessor/c-cpp-preprocessor-reference.md)  
 매크로, 연산자 및 지시문을 변환 하 여 컴파일러에 대 한 소스 파일을 준비 하는 전처리기에 설명 합니다.  
  
 [사용자 지정 빌드 단계 및 빌드 이벤트 이해](../../ide/understanding-custom-build-steps-and-build-events.md)  
 빌드 프로세스를 사용자 지정에 대해 설명 합니다.  
  
 [C/c + + 프로그램 빌드](../../build/building-c-cpp-programs.md)  
 명령줄 또는 Visual Studio의 통합 개발 환경에서 프로그램 빌드를 설명하는 항목에 대한 링크를 제공합니다.  
  
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)  
 개발 환경에서 또는 명령줄에서 컴파일러 옵션 설정에 설명합니다.  
  
 [컴파일러 옵션](../../build/reference/compiler-options.md)  
 컴파일러 옵션을 사용 하 여 설명 하는 항목에 대 한 링크를 제공 합니다.  
  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)  
 통합된 개발 환경 외부 링커 옵션 설정에 설명합니다.  
  
 [링커 옵션](../../build/reference/linker-options.md)  
 링커 옵션을 사용 하 여 설명 하는 항목에 대 한 링크를 제공 합니다.  
  
 [BSCMAKE 참조](../../build/reference/bscmake-reference.md)  
 Microsoft 찾아보기 Information Maintenance Utility (BSCMAKE 설명. EXE)가 있는 빌드 찾아보기 정보 파일 (.bsc)에 대해 설명 컴파일 중에 만들어진 파일입니다.  
  
 [LIB 참조](../../build/reference/lib-reference.md)  
 만들고 개체 파일 형식 COFF (공용) 개체 파일의 라이브러리를 관리 하는 Microsoft 라이브러리 관리자 (LIB.exe)에 대해 설명 합니다.  
  
 [EDITBIN 참조](../../build/reference/editbin-reference.md)  
 Microsoft COFF Binary 파일 편집기 (EDITBIN 합니다. 이진 파일이 COFF 공용 개체 파일 형식 ()를 수정 하는 EXE).  
  
 [DUMPBIN 참조](../../build/reference/dumpbin-reference.md)  
 Microsoft COFF Binary File Dumper (DUMPBIN 설명. Exe)에 일반적인 COFF 개체 파일 형식 () 이진 파일에 대 한 정보입니다.  
  
 [NMAKE 참조](../../build/nmake-reference.md)  
 Microsoft Program Maintenance Utility (NMAKE 설명. EXE)는 프로젝트를 빌드하는 도구 설명 파일에 포함 된 명령을 기반으로 합니다.