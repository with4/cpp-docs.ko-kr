---
title: "C/C++ 속성(Linux C++) | Microsoft Docs"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bb8894b-c874-4a68-935e-b127d54e484f
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.VCClangCompilerTool.AdditionalIncludeDirectories
- VC.Project.VCClangCompilerTool.DebugInformationFormat
- VC.Project.VCClangCompilerTool.ObjectFile
- VC.Project.VCClangCompilerTool.WarningLevel
- VC.Project.VCClangCompilerTool.WarnAsError
- VC.Project.VCClangCompilerTool.AdditionalWarning
- VC.Project.VCClangCompilerTool.Verbose
- VC.Project.VCConfiguration.BuildLogFile
- VC.Project.VCClangCompilerTool.Optimization
- VC.Project.VCClangCompilerTool.StrictAliasing
- VC.Project.VCClangCompilerTool.UnrollLoops
- VC.Project.VCClangCompilerTool.LinkTimeOptimization
- VC.Project.VCClangCompilerTool.OmitFramePointers
- VC.Project.VCClangCompilerTool.NoCommonBlocks
- VC.Project.VCClangCompilerTool.PIC
- VC.Project.VCClangCompilerTool.ThreadSafeStatics
- VC.Project.VCClangCompilerTool.RelaxIEEE
- VC.Project.VCClangCompilerTool.HideInlineMethods
- VC.Project.VCClangCompilerTool.SymbolsHiddenByDefault
- VC.Project.VCClangCompilerTool.ExceptionHandling
- VC.Project.VCClangCompilerTool.RuntimeTypeInfo
- VC.Project.VCClangCompilerTool.CLanguageStandard
- VC.Project.VCClangCompilerTool.CppLanguageStandard
- VC.Project.VCClangCompilerTool.PreprocessorDefinitions
- VC.Project.VCClangCompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCClangCompilerTool.UndefineAllPreprocessorDefinitions
- VC.Project.VCClangCompilerTool.ShowIncludes
- VC.Project.VCClangCompilerTool.CompileAs
- VC.Project.VCClangCompilerTool.ForcedIncludeFiles
- vc.project.AdditionalOptionsPage
ms.openlocfilehash: 94a22843c15e537a7af8e1e44827f8c1ab365165
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="cc-properties-linux-c"></a>C/C++ 속성(Linux C++)

## <a name="general"></a>일반
속성 | 설명 | 선택 항목
--- | ---| ---
추가 포함 디렉터리 | 포함 경로에 추가할 디렉터리를 하나 이상 지정합니다. 항목이 여러 개일 때에는 세미콜론으로 구분합니다. (-I[path]).
디버그 정보 형식 | 컴파일러에서 생성되는 디버깅 정보 형식을 지정합니다. | **없음** - 디버깅 정보를 생성하지 않으므로 컴파일이 더 빨라질 수 있습니다.<br>**최소 디버그 정보** - 최소한의 디버그 정보를 생성합니다.<br>**전체 디버그 정보(DWARF2)** - DWARF2 디버그 정보를 생성합니다.<br>
개체 파일 이름 | 기본 개체 파일 이름을 재정의할 이름을 지정합니다. 파일 또는 디렉터리 이름일 수 있습니다. (-o [name]).
경고 수준 | 컴파일러가 코드 오류를 처리하는 수준을 선택합니다.  다른 플래그는 추가 옵션에 직접 추가해야 합니다. (/w, /Weverything). | **모든 경고 해제** - 모든 컴파일러 경고를 해제합니다.<br>**모든경고사용** - 기본적으로 해제되어 있는 경고를 포함한 모든 경고를 사용하도록 설정합니다.<br>
경고를 오류로 처리 | 모든 컴파일러 경고를 오류로 처리합니다. 새 프로젝트인 경우 모든 컴파일에서 /Werror를 사용하는 것이 좋습니다. 모든 경고를 해결하면 찾기 어려운 코드 오류를 최소화할 수 있습니다.
C 추가 경고 | 추가 경고 메시지 집합을 정의합니다.
C++ 추가 경고 | 추가 경고 메시지 집합을 정의합니다.
자세한 정보 표시 모드 사용 | 자세한 정보 표시 모드가 설정되면 이 도구는 빌드를 진단하기 위한 추가 정보를 출력합니다.
C 컴파일러 | 원격 시스템에서 C 소스 파일을 컴파일하는 동안 호출할 프로그램 또는 C 컴파일러 경로를 지정합니다.
C++ 컴파일러 | 원격 시스템에서 C++ 소스 파일을 컴파일하는 동안 호출할 프로그램 또는 C++ 컴파일러 경로를 지정합니다.
컴파일 시간 제한 | 원격 컴파일 시간 제한(밀리초)입니다.
개체 파일 복사 | 원격 시스템에서 로컬 컴퓨터로 컴파일한 개체 파일을 복사할지 여부를 지정합니다.

## <a name="optimization"></a>최적화
속성 | 설명 | 선택 항목
--- | ---| ---
최적화 | 응용 프로그램의 최적화 수준을 지정합니다. | **사용자 지정** - 사용자 지정 최적화<br>**사용 안 함** - 최적화를 사용하지 않습니다.<br>**크기 최소화** - 크기에 맞게 최적화합니다.<br>**속도 최대화** - 크기에 맞게 최적화합니다.<br>**전체 최적화** - 고가의 최적화입니다.<br>
엄격한 앨리어싱 | 가장 엄격한 앨리어싱 규칙을 가정합니다.  한 형식의 개체는 다른 형식의 개체와 동일한 주소에 있을 수 없는 것으로 간주됩니다.
루프 언롤 | 더 큰 코드 크기를 희생하는 대신 실행된 분기의 수를 줄여 응용 프로그램 속도를 높이도록 루프를 언롤합니다.
링크 타임 최적화 | 최적화 프로그램이 응용 프로그램에 있는 개체 파일을 살펴볼 수 있도록 허용하여 절차 간 최적화를 사용하도록 설정합니다.
프레임 포인터 생략 | 호출 스택에서 프레임 포인터를 생성하지 않습니다.
공용 블록 없음 | 일반 블록으로 생성하는 대신 개체 파일의 데이터 섹션에서 초기화되지 않은 전역 변수까지 할당합니다.

## <a name="preprocessor"></a>전처리기
속성 | 설명 | 선택 항목
--- | ---| ---
전처리기 정의 | 소스 파일에 대한 전처리 기호를 정의합니다. (-D)
전처리기 정의 해제 | 전처리기 정의 해제를 하나 이상 지정합니다.  (-U [macro])
모든 전처리기 정의 해제 | 이전에 정의한 모든 전처리기 값을 정의 해제합니다.  (-undef)
포함 표시 | 컴파일러 출력으로 포함 파일 목록을 생성합니다.  (-H)

## <a name="code-generation"></a>코드 생성
속성 | 설명 | 선택 항목
--- | ---| ---
위치 독립적 코드 | 공유 라이브러리에서 사용할 PIC(위치 독립적 코드)를 생성합니다.
정적은 스레드로부터 안전합니다. | 로컬 정적의 스레드 안전 초기화를 위해 C++ ABI에 지정된 루틴을 사용하도록 추가 코드를 내보냅니다. | **아니요** - 스레드로부터 안전한 정적을 사용하지 않도록 설정합니다.<br>**예** - 스레드로부터 안전한 정적을 사용하도록 설정합니다.<br>
부동 소수점 최적화 | IEEE-754 규격을 완화하여 부동 소수점을 최적화할 수 있도록 합니다.
인라인 메서드 숨김 | 사용하도록 설정되면 인라인 메서드의 확장 복사본이 'private extern'으로 선언됩니다.
기본적으로 기호 숨김 | '__attribute' 매크로를 사용하여 내보내도록 명시적으로 표시되지 않는 한 모든 기호는 'private extern'으로 선언됩니다.
C++ 예외 사용 | 컴파일러가 사용하는 예외 처리 모델을 지정합니다. | **아니요** - 예외 처리를 사용하지 않도록 설정합니다.<br>**예** - 예외 처리를 사용하도록 설정합니다.<br>

## <a name="language"></a>언어
속성 | 설명 | 선택 항목
--- | ---| ---
런타임 형식 정보 사용 | 런타임에 C++ 개체의 형식(런타임 형식 정보)을 검사하는 코드를 추가합니다.     (frtti, fno-rtti)
C 언어 표준 | C 언어 표준을 결정합니다. | **기본**<br>**C89** - C89 언어 표준입니다.<br>**C99** - C99 언어 표준입니다.<br>**C11** - C11 언어 표준입니다.<br>**C99(GNU 언어)** - C99(GNU 언어) 언어 표준입니다.<br>**C11(GNU 언어)** - C11(GNU 언어) 언어 표준입니다.<br>
C++ 언어 표준 | C++ 언어 표준을 결정합니다. | **기본**<br>**C++03** - C++03 언어 표준입니다.<br>**C++11** - C++11 언어 표준입니다.<br>**C++14** - C++14 언어 표준입니다.<br>**C++03(GNU 언어)** - C++03(GNU 언어) 언어 표준입니다.<br>**C++11(GNU 언어)** - C++11(GNU 언어) 언어 표준입니다.<br>**C++14(GNU 언어)** - C++14(GNU 언어) 언어 표준입니다.<br>

## <a name="advanced"></a>고급
속성 | 설명 | 선택 항목
--- | ---| ---
다음으로 컴파일 | .c 및 .cpp 파일에 대한 컴파일 언어 옵션을 선택합니다.  '기본값'은 .c 또는 .cpp 확장명에 따라 감지됩니다. (-x c, -x c++) | **기본값** - 기본값입니다.<br>**C 코드로 컴파일** - C 코드로 컴파일합니다.<br>**C++ 코드로 컴파일** - C++ 코드로 컴파일합니다.<br>
강제 포함 파일 | 하나 이상의 강제 포함 파일입니다. (-include [이름])

## <a name="additional-options"></a>추가 옵션 
