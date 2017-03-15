---
title: "Visual Studio의 Visual C++에 대한 새로운 기능 | Microsoft 문서"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: BrianPeek
ms.author: brpeek
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 39648d170fc189168d5f199fff8b3c2012456b82
ms.openlocfilehash: 89fceaf02fe2b02bfe2ce6ff1de90bcd2bf66006

---

# <a name="whats-new-for-visual-c-in-includevsdev15mdmiscincludesvsdev15mdmd"></a>[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]의 Visual C++에 대한 새로운 기능

[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]에는 Visual C++ 환경에 대한 많은 업데이트와 수정이 포함되어 있습니다. 컴파일러 및 도구에서 250개 이상의 버그와 보고된 문제가 해결되었으며, 그 중 상당수는 고객이 [Microsoft Connect](https://connect.microsoft.com/VisualStudio "Microsoft Connect")를 통해 제출한 것들입니다. 버그를 알려 주셔서 감사합니다.  모든 Visual Studio의 새로운 기능에 대한 자세한 내용은 [[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]의 새로운 기능](https://go.microsoft.com/fwlink/?linkid=834481)을 참조하세요.

[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]의 컴파일러 및 도구 버전 번호는 14.10.24629입니다. 


## <a name="c-compiler"></a>C++ 컴파일러

### <a name="c-conformance-improvements"></a>C++ 규칙 향상
이 릴리스에서는 C++ 컴파일러 및 표준 라이브러리를 C++11 및 C++14 기능에 대한 강화된 지원 기능과, C++17 표준에서 선보일 것으로 예상되는 특정 기능에 대한 임시 지원 기능으로 업데이트했습니다. 자세한 내용은 [Visual Studio 2017의 C++ 규칙 향상](cpp-conformance-improvements-2017.md)을 참조하세요.

### <a name="new-compiler-switches"></a>새 컴파일러 스위치  

 -**/std:c++14** 및 **/std:c++latest**: 이러한 컴파일러 스위치를 사용하면 프로젝트에서 특정 버전의 ISO C++ 프로그래밍 언어를 옵트인(opt in)할 수 있습니다. 자세한 내용은 [컴파일러의 표준 버전 스위치](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/standards-version-switches-in-the-compiler)를 참조하세요. /std:c++latest 스위치는 대부분의 새 초안 표준 기능을 보호합니다. 

-[/permissive-](build/reference/permissive-standards-conformance.md): 모든 엄격한 표준 준수 컴파일러 옵션을 사용하고 대부분의 Microsoft 전용 컴파일러 확장(예: __declspec(dllimport) 제외)을 사용하지 않도록 설정합니다. 기본적으로 꺼져 있지만 이후 특정 시점에는 기본적으로 켜질 예정입니다.

-[/diagnostics](build/reference/diagnostics-compiler-diagnostic-options.md): 줄 번호, 줄 번호 및 열 또는 줄 번호 및 열과 진단 오류 또는 경고가 발견된 코드 줄 아래의 캐럿 표시를 사용합니다.

-[/debug:fastlink](build/reference/debug-generate-debug-info.md):  
일부 디버그 정보를 PDB 파일에 복사하지 않음으로써 최대 30%까지 빠른 증분 연결 시간(Visual Studio 2015 대비)을 사용합니다. 대신, PDB 파일은 실행 파일을 만드는 데 사용된 개체 및 라이브러리 파일에 대한 디버그 정보를 가리킵니다. [Faster C++ build cycle in VS “15” with /Debug:fastlink](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/faster-c-build-cycle-in-vs-15-with-debugfastlink/)(/Debug:fastlink를 사용하는 VS “15”의 더 빠른 C++ 빌드 주기) 및 [Recommendations to speed C++ builds in Visual Studio](https://blogs.msdn.microsoft.com/vcblog/2016/10/26/recommendations-to-speed-c-builds-in-visual-studio/)(Visual Studio에서 C++ 빌드 속도를 향상하기 위한 권장 사항)를 참조하세요.

[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]에서는 /sdl과 함께 /await를 사용할 수 있습니다. 코루틴에서 /RTC 제한이 제거되었습니다. 

### <a name="codegen-security-diagnostics-and-versioning"></a>Codegen, 보안, 진단 및 버전 관리
이 릴리스에서는 최적화, 코드 생성, 도구 집합 버전 관리 및 진단의 몇 가지 기능이 향상되었습니다. 특히 주목할 만한 기능 향상은 다음과 같습니다.  

- 루프의 코드 생성 향상: 상수 정수 나누기의 자동 벡터화를 지원하며, memset 패턴 식별 기능이 향상되었습니다.
- 코드 보안 개선: 버퍼 오버런 컴파일러 진단의 내보내기가 개선되었으며, 이제는 /guard:cf가 점프 테이블을 생성하는 스위치 문을 보호합니다.
- 버전 관리: 기본 제공 전처리기 매크로 _MSC_VER의 값이 이제 Visual C++ 도구 집합 업데이트 시마다 일정하게 업데이트됩니다. 자세한 내용은 [Visual C++ Compiler Version](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/visual-c-compiler-version/)(Visual C++ 컴파일러 버전)을 참조하세요.
- 새 도구 집합 레이아웃: 개발 컴퓨터에서 컴파일러 및 관련된 빌드 도구의 위치 및 디렉터리 구조가 변경되었습니다. 새 레이아웃을 사용하면 여러 버전의 컴파일러를 병렬 설치할 수 있습니다. 자세한 내용은 [Compiler Tools Layout in Visual Studio “15”](https://blogs.msdn.microsoft.com/vcblog/2016/10/07/compiler-tools-layout-in-visual-studio-15/)(Visual Studio "15"의 컴파일러 도구 레이아웃)를 참조하세요.
- 향상된 진단: 이제 출력 창에 오류가 발생하는 열이 표시됩니다. 자세한 내용은 [C++ compiler diagnostics improvements in VS “15” Preview 5](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/c-compiler-diagnostics-improvements-in-vs-15-rc/)(VS "15" Preview 5의 C++ 컴파일러 진단 향상)를 참조하세요.

## <a name="c-libraries"></a>C++ 라이브러리

### <a name="standard-library-improvements"></a>표준 라이브러리 향상:

* basic_string _ITERATOR_DEBUG_LEVEL != 0 진단 기능이 조금 향상되었습니다. 문자열 조직에서 IDL 검사를 트립할 경우 그 트립이 일어나게 된 특정 동작이 보고됩니다. 예를 들어 "문자열 반복기를 역참조할 수 없음" 대신에 "범위(예: 끝 반복기) 밖에 있기 때문에 문자열 반복기를 역참조할 수 없음”이라는 메시지가 나타납니다.
* 성능 향상: basic_string::find(char) 오버로드가 traits::find를 한 번만 호출합니다. 이전에 이 오버로드는 길이가 1인 문자열을 대상으로 한 일반 문자열 검색으로 구현되었습니다.
* 성능 향상: basic_string::operator==가 문자열 내용을 비교하기 전에 문자열 크기를 확인합니다.
* 성능 향상: basic_string에서 컴파일러 최적화 프로그램의 분석 작업을 어렵게 한 컨트롤 결합을 제거했습니다. VSO# 262848 "<string>: reserve()의 작업이 너무 많습니다”를 해결했습니다. 그래도 짧은 문자열을 대상으로 reserve를 호출할 때 아무 작업도 하지 않도록 하는 데 비용이 듭니다.
* \<any\>, \<string_view\>, apply(), make_from_tuple()을 추가했습니다.
* std::vector가 정확성과 성능에서 철저히 점검되었습니다. 이제 삽입/대입 작업에서 앨리어싱이 표준에서 요구하는 대로 올바르게 처리되고, 강한 예외 보장이 표준에 따라 요구되면 move_if_noexcept() 및 기타 논리를 통해 제공되며, 삽입/대입의 항목 작업 개수가 줄어들었습니다.
* 이제 C++ 표준 라이브러리가 가상의 null 포인터를 역참조하지 못하도록 방지합니다.
* \<옵션\>, \<variant\>, shared_ptr::weak_type 및 \<cstdalign\>이 추가되었습니다.
* min/max/minmax(initializer_list) 및 min_element/max_element/minmax_element()에 C++14 constexpr을 사용할 수 있게 되었습니다.
* weak_ptr::lock() 성능이 향상되었습니다.
* 이전에 코드가 영원히 잠기는 문제가 발생하던 std::promise의 이동 할당 연산자가 해결되었습니다.
* atomic\<T \*\>를 T \*로 암시적으로 변환할 때 발생하는 컴파일러 오류를 해결했습니다.
* pointer_traits\<Ptr\>이 이제 Ptr::rebind\<U\>를 올바르게 검색합니다.
* move_iterator의 빼기 연산자에서 누락된 const 한정자가 해결되었습니다.
* propagate_on_container_copy_assignment 및 propagate_on_container_move_assignment를 요청하는 상태 저장 사용자 정의 할당자에 대한 잘못된 자동 코드 생성이 해결되었습니다.
* 이제 atomic\<T\>가 오버로드된 operator&()를 허용합니다.
* 컴파일러 처리량을 늘리기 위해 이제 C++ 표준 라이브러리 헤더는 불필요한 컴파일러 내장 함수에 대한 선언을 포함하지 않습니다.
* 잘못된 bind() 호출에 대한 컴파일러 진단이 약간 개선되었습니다.
* std::string/std::wstring의 이동 생성자 성능이 3배 넘게 향상됨

### <a name="open-source-library-support"></a>오픈 소스 라이브러리 지원  
vcpkg는 오픈 소스 명령줄 도구로, Visual Studio에서 오픈 소스 C++ 정적 라이브러리와 DLL을 얻고 빌드하는 프로세스를 훨씬 간소화합니다. 자세한 내용은 [Vcpkg updates: Static linking is now available](https://blogs.msdn.microsoft.com/vcblog/2016/11/01/vcpkg-updates-static-linking-is-now-available/)(vcpkg 업데이트: 이제 정적 연결을 사용할 수 있음)을 참조하세요.

### <a name="cpprest-sdk-290"></a>CPPRest SDK 2.9.0  
C++용 플랫폼 간 웹 API인 CPPRestSDK가 버전 2.9.0으로 업데이트되었습니다. 자세한 내용은 [CppRestSDK 2.9.0 is available on GitHub](https://blogs.msdn.microsoft.com/vcblog/2016/10/21/cpprestsdk-2-9-0-is-available-on-github/)(GitHub에서 CppRestSDK 2.9.0을 사용할 수 있음)를 참조하세요.

### <a name="atl"></a>ATL
* 이름 조회 규칙의 다른 설정 수정
* 기존 이동 생성자 및 이동 할당 연산자가 이제 throw되지 않음으로 제대로 표시됨
* atlstr.h에서 지역 정적 변수의 스레드 안전 초기화에 대한 올바른 경고 C4640 표시
* [ATL 사용 및 DLL 빌드] 시 XP 도구 집합에서 지역 정적의 스레드 안전 초기화가 자동으로 꺼집니다. 물론 이에 해당하는 경우는 더 이상 없습니다. 스레드 안전 초기화 해제를 원하는 경우 프로젝트 설정에 /Zc:threadSafeInit-을 추가할 수 있습니다. 

## <a name="c-ide"></a>C++ IDE

### <a name="intellisense"></a>IntelliSense  
* 이제 새 SQLite 기반 데이터베이스 엔진이 기본적으로 사용됩니다. 이 엔진은 정의로 이동(Go To Definitions), 모든 참조 찾기(Find All References) 같은 데이터베이스 작업의 속도를 높이고 초기 솔루션 구문 분석 시간을 크게 개선합니다. 해당 설정이 도구 > 옵션 > 텍스트 편집기 > C/C++ > 고급(이전에는 ...C/C++ > 실험적에 있었음)으로 이동되었습니다.

* 미리 컴파일된 헤더를 사용하지 않는 프로젝트 및 파일에 대한 IntelliSense 성능이 향상되었습니다. 현재 파일의 헤더에 대해 자동 미리 컴파일된 헤더가 생성됩니다.

* IntelliSense 오류에 대한 오류 필터링 및 도움말이 오류 목록에 추가되었습니다. 이제 오류 열을 클릭하여 필터링할 수 있습니다. 또한 특정 오류를 클릭하거나 F1 키를 누르면 오류 메시지에 대한 온라인 검색이 시작됩니다.

  ![오류 목록](media/ErrorList1.png "오류 목록")

  ![오류 목록 필터링](media/ErrorList2.png "오류 목록 필터링")

* 멤버 목록 항목을 종류별로 필터링하는 기능이 추가되었습니다.

  ![멤버 목록 필터링](media/mlfiltering.png "멤버 목록 필터링")

* 멤버 목록에 나타나는 항목의 컨텍스트 인식 필터링을 제공하는 새로운 실험 예측 IntelliSense 기능이 추가되었습니다. [C++ IntelliSense Improvements – Predictive IntelliSense & Filtering](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/c-intellisense-improvements-predictive-intellisense-filtering/)(C++ IntelliSense 향상 – 예측 IntelliSense 및 필터링)을 참조하세요.

* 이제 모든 참조 찾기(Shift+F12)를 사용하여 복잡한 코드베이스에서도 쉽게 탐색할 수 있습니다. 고급 그룹화, 필터링, 정렬, 결과 내 검색 및 (일부 언어의 경우) 색 지정이 제공되므로 참조를 명확하게 이해할 수 있습니다. C++의 경우 새로운 UI에 변수에서 읽고 있는지 아니면 변수에 쓰고 있는지에 대한 정보가 포함되어 있습니다.

* _**RC의 새 기능**_ IntelliSense 점-화살표 기능이 실험적에서 고급으로 옮겨졌고 이제 기본적으로 활성화됩니다. 편집기 기능인 범위 확장과 우선 순위 확장도 실험적에서 고급으로 옮겨졌습니다.

* _**RC의 새 기능**_ 실험적 리팩터링 기능인 시그니처 변경과 함수 추출이 기본적으로 활성화됩니다.

* _**RC의 새 기능**_ C++ 프로젝트 ‘빠른 프로젝트 로드’를 위한 새로운 실험적 기능을 활성화했습니다. 다음에 C++ 프로젝트를 열 때 프로젝트가 더 빠르게 로드되고, 그 다음에 프로젝트를 열 때는 더 빠르게 로드됩니다.

이러한 기능 중 일부는 다른 언어에 공통적으로 적용되고, 일부는 C++에만 해당합니다. 이러한 새로운 기능에 대한 자세한 내용은 [Announcing Visual Studio “15”](https://blogs.msdn.microsoft.com/visualstudio/2016/10/05/announcing-visual-studio-15-preview-5/)(Visual Studio “15” 발표)를 참조하세요. 

### <a name="support-for-non-msbuild-projects-with-open-folder"></a>폴더 열기를 사용한 비 MSBuild 프로젝트에 대한 지원
Visual Studio 2017에서는 솔루션 또는 프로젝트를 만들 필요 없이 소스 코드가 포함된 폴더에서 코딩, 빌드 및 디버그할 수 있는 "폴더 열기" 기능이 도입되었습니다. 이렇게 하면 프로젝트가 MSBuild 기반 프로젝트가 아닌 경우에도 Visual Studio를 훨씬 간단하게 시작할 수 있습니다. "폴더 열기"를 사용하면 Visual Studio에서 MSBuild 프로젝트에 이미 제공하는 강력한 코드 이해, 편집, 빌드 및 디버깅 기능에 액세스할 수 있습니다. 자세한 내용은 [Bring your C++ codebase to Visual Studio with “Open Folder”](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/bring-your-c-codebase-to-visual-studio-with-open-folder/)("폴더 열기"를 사용하여 C++ 코드베이스를 Visual Studio로 가져오기)를 참조하세요.

* _**RC의 새 기능**_ 폴더 열기 환경을 개선했습니다.     
다음 json 파일을 통해 환경을 사용자 지정할 수 있습니다.
  -    IntelliSense 및 검색 환경을 사용자 지정할 수 있는 CppProperties.json.
  -    빌드 단계를 사용자 지정할 수 있는 Tasks.json. 
  -    디버깅 환경을 사용자 지정할 수 있는 Launch.json.

### <a name="cmake-support-via-open-folder"></a>폴더 열기를 사용한 CMake 지원
Visual Studio 2017에서는 MSBuild 프로젝트 파일(.vcxproj)로 변환하지 않고 CMake 프로젝트를 사용할 수 있는 지원이 도입되었습니다. 자세한 내용은 [CMake support in Visual Studio](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/cmake-support-in-visual-studio/)(Visual Studio의 CMake 지원)를 참조하세요. “폴더 열기”로 CMake 프로젝트를 여는 경우 C++ 편집, 빌드, 디버깅 환경이 자동으로 구성됩니다.

* _**RC의 새 기능**_ C++ IntelliSense가 루트 폴더에 CppProperties.json 파일을 만들지 않아도 작동합니다. 이와 함께 CMake 파일과 CppProperties.json 파일에서 제공하는 구성을 서로 쉽게 전환할 수 있도록 새 드롭다운을 추가했습니다.

* _**RC의 새 기능**_ CMakeLists.txt 파일과 같은 폴더에 있는 CMakeSettings.json 파일을 통해 추가 구성이 지원됩니다.

  ![Cmake 폴더 열기](media/cmake_cpp.png "Cmake 폴더 열기")


## <a name="c-installation-workloads"></a>C++ 설치 워크로드 

### <a name="windows-desktop-development-with-c"></a>C++을 사용한 Windows 데스크톱 개발:  
이제 원래 C++ 워크로드에 대한 보다 세분화된 설치 환경이 제공됩니다. 필요한 도구만 설치할 수 있도록 선택 가능한 구성 요소가 추가되었습니다.  설치 관리자 UI에 나열된 구성 요소에 대해 표시된 설치 크기는 정확하지 않으며 전체 크기는 이보다 클 수 있습니다.  

### <a name="linux-development-with-c"></a>C++를 사용한 Linux 개발:  
일반적으로 사용되는 확장인 [Linux 개발용 Visual C++](https://visualstudiogallery.msdn.microsoft.com/725025cf-7067-45c2-8d01-1e0fd359ae6e)가 Visual Studio에 포함됩니다. 이 설치는 Linux 환경에서 실행되는 C++ 응용 프로그램을 개발 및 디버깅하는 데 필요한 모든 사항을 제공합니다.  

### <a name="game-development-with-c"></a>C++를 사용한 게임 개발:  
C++의 모든 기능을 사용하여 DirectX 또는 Cocos2d로 구동하는 전문 게임을 개발해 보세요.  

### <a name="mobile-development-with-c-android-and-ios"></a>C++를 사용한 모바일 개발(Android 및 iOS):  
이제 Visual Studio를 사용하여 Android 및 iOS를 대상으로 할 수 있는 모바일 앱을 만들고 디버깅할 수 있습니다.  

### <a name="universal-windows-apps"></a>유니버설 Windows 앱:  
C++는 유니버설 Windows 앱 워크로드에 대한 선택적 구성 요소로 제공됩니다.  

## <a name="new-options-for-c-on-universal-windows-platform"></a>유니버설 Windows 플랫폼의 C++에 대한 새로운 옵션
이제 유니버설 Windows 플랫폼 및 Windows 스토어용 C++ 응용 프로그램을 작성하고 패키징하기 위한 새로운 옵션이 있습니다. Windows 스토어를 통해 배포하기 위해 데스크톱 앱 변환기를 사용하여 기존 데스크톱 응용 프로그램을 패키징할 수 있습니다. 자세한 내용은 [Using Visual C++ Runtime in Centennial project](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project/)(Centennial 프로젝트에서 Visual C++ 런타임 사용) 및 [데스크톱 브리지를 사용하여 데스크톱 앱을 UWP(유니버설 Windows 플랫폼)로 가져오기](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root)를 참조하세요.

이제 새 코드를 작성할 때 헤더 파일에서만 구현되는 Windows 런타임용 표준 C++ 언어 프로젝션인 C++/WinRT를 사용할 수 있습니다. C++/WinRT를 사용하면 모든 표준 규격 C++ 컴파일러를 통해 Windows 런타임 API를 작성하고 사용할 수 있습니다. C++/WinRT는 C++ 개발자에게 최신 Windows API에 대한 최고 수준의 액세스를 제공하도록 설계되었습니다. 자세한 내용은 [C++/WinRT Available on GitHub](https://moderncpp.com/)(GitHub에서 C++/WinRT를 사용할 수 있음)를 참조하세요.


## <a name="clangc2-platform-toolset"></a>Clang/C2 플랫폼 도구 집합
[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]와 함께 제공되는 Clang/C2 도구 집합이 대규모 프로젝트를 빌드하는 데 중요한 /bigobj 스위치를 지원합니다. 또한 컴파일러의 프런트 엔드와 백 엔드에서 몇몇 중요한 버그 수정이 있었습니다.

## <a name="c-code-analysis"></a>C++ 코드 분석

[C++ Core 지침](https://github.com/isocpp/CppCoreGuidelines)을 적용하기 위한 C++ Core Checkers가 이제는 Visual Studio와 함께 배포됩니다. 프로젝트의 속성 페이지의 코드 분석 확장 대화 상자에서 체커를 활성화하기만 하면 코드 분석을 실행할 때 확장이 포함됩니다. 

![CppCoreCheck](media/CppCoreCheck.png "CppCoreCheck 속성 페이지") 

## <a name="visual-studio-graphics-diagnostics"></a>Visual Studio 그래픽 진단

Visual Studio 그래픽 진단은 Direct3D 앱의 렌더링 및 성능 문제를 기록한 후 분석하기 위한 도구 집합입니다. Windows PC에서 로컬로 실행 중이거나 Windows 장치 에뮬레이터 또는 원격 PC나 장치에서 실행 중인 앱에서 그래픽 진단 기능을 사용할 수 있습니다.

* **꼭짓점 및 기하 도형 셰이더의 입력 및 출력:** 꼭짓점 셰이더 및 기하 도형 셰이더의 입력과 출력을 볼 수 있는 기능은 가장 많이 요청된 기능 중 하나였으며 이제 도구에서 지원됩니다. 파이프라인 단계 보기에서 VS 또는 GS 단계를 선택하면 아래 표의 입력 및 출력 검사가 시작됩니다.

  ![셰이더의 입력/출력](media/io-shaders.png)

* **개체 테이블에서 검색 및 필터링:** 찾으려는 리소스를 빠르고 쉽게 찾는 방법을 제공합니다.

  ![검색](media/search.png)
   
* **리소스 기록:** 이 새로운 보기를 통해 캡처된 프레임 렌더링 시 사용된 리소스의 전체 수정 기록을 간단하게 확인할 수 있습니다. 리소스에 대한 기록을 호출하려면 리소스 하이퍼링크 옆에 있는 시계 아이콘을 클릭하면 됩니다.

  ![리소스 기록](media/resource-history.png)

  리소스의 변경 기록으로 채워진 새 리소스 기록 도구 창이 표시됩니다.

  ![리소스 기록 변경](media/resource-history-change.png)

  전체 호출 스택 캡처링을 사용하여 프레임이 캡처된 경우(**Visual Studio > 도구 > 옵션 > 그래픽 진단**), 각 변경 이벤트의 컨텍스트를 신속하게 추론하고 Visual Studio 프로젝트 내에서 검사할 수 있습니다.  

* **API 통계:** 프레임의 API 사용에 대한 대략적인 요약을 표시합니다. 인지하지 못한 상태에서 수행 중인 호출이나 너무 많이 수행 중인 호출을 검색하는 데 유용할 수 있습니다. 이 창은 Visual Studio Graphics Analyzer의 **보기 > API 통계**를 통해 사용할 수 있습니다.

  ![API 통계](media/api-stats.png)

* **메모리 통계:** 드라이버가 프레임에 생성되는 리소스에 대해 할당하는 메모리 양을 표시합니다. 이 창은 Visual Studio Graphics Analyzer의 보기 > 메모리 통계를 통해 사용할 수 있습니다. 마우스 오른쪽 단추로 클릭하고 모두 복사를 선택하여 데이터를 CSV 파일에 복사한 후 스프레드시트에서 볼 수 있습니다.

  ![메모리 통계](media/memory-stats.png)
 
* **프레임 유효성 검사:** 새로운 오류 및 경고 목록을 통해 Direct3D 디버그 계층에서 검색된 잠재적인 문제에 따라 이벤트 목록을 쉽게 탐색할 수 있습니다. Visual Studio Graphics Analyzer에서 보기 -> 프레임 유효성 검사를 클릭하여 창을 엽니다. 그런 다음 유효성 검사 실행을 클릭하여 분석을 시작합니다. 프레임의 복잡성에 따라 완료하는 데 몇 분 정도 걸릴 수 있습니다.

  ![프레임 유효성 검사](media/frame-validation.png)
 
* **D3D12에 대한 프레임 분석:** 프레임 분석을 사용하여 안내된 "가상 분석" 실험을 통해 그리기 호출 성능을 분석할 수 있습니다. 프레임 분석 탭으로 전환한 다음 분석을 실행하여 보고서를 표시합니다. 자세한 내용을 보려면 [GoingNative 25: Visual Studio Graphics Frame Analysis](https://channel9.msdn.com/Shows/C9-GoingNative/GoingNative-25-Offline-Analysis-Graphics-Tool)(GoingNative 25: Visual Studio 그래픽 프레임 분석) 동영상을 시청하세요.

  ![프레임 분석](media/frame-analysis.png)

* **GPU 사용량 향상:** 보다 자세한 분석을 위해 GPU 보기 또는 WPA(Windows 성능 분석기) 도구를 사용하여 Visual Studio GPU 사용량 프로파일러를 통해 수행된 추적을 엽니다. Windows 성능 도구 키트가 설치되어 있는 경우 WPA 및 GPU 보기를 위한 두 개의 하이퍼링크가 세션 개요의 오른쪽 아래에 표시됩니다.

  ![GPU 사용량](media/gpu-usage.png)
 
  이 링크를 통해 GPU 보기에서 열린 추적은 VS와 GPU 보기 간에 동기화된 타임라인 확대/축소 및 이동을 지원합니다. VS의 확인란을 사용하여 동기화 사용 여부를 제어합니다. 

  ![GPU 보기](media/gpu-view.png) 


 


<!--HONumber=Feb17_HO4-->


