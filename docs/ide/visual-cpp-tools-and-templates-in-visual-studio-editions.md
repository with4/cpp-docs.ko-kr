---
title: "Visual Studio 버전의 Visual C++ 도구 및 템플릿 | Microsoft Docs"
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
  - "버전[C++]"
  - "버전[C++]"
  - "Visual C++, 버전"
ms.assetid: 3d88607b-9cc4-490a-8d4c-31ee7610a26f
caps.latest.revision: 51
caps.handback.revision: 51
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual Studio 버전의 Visual C++ 도구 및 템플릿
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 표에는 Visual Studio에서 사용할 수 있는 Visual C\+\+ 기능이 나와 있습니다.  셀에 X가 있으면 해당 기능을 사용할 수 있음을 나타내고, 셀이 비어 있으면 해당 기능을 사용할 수 없음을 나타냅니다.  괄호 안의 참고 사항은 해당 기능을 사용할 수 있지만 제한됨을 나타냅니다.  
  
## 플랫폼  
  
||||||  
|-|-|-|-|-|  
|플랫폼|Visual Studio Express for Windows 10|Visual Studio Express for Windows Desktop|Visual Studio Community\/Professional|Visual Studio Enterprise|  
|Windows 바탕 화면||X|X|X|  
|범용 Windows 플랫폼\(휴대폰, 태블릿, PC, Xbox, IoT 및 HoloLens\)|X||X|X|  
|Windows 스토어 8.1|||X|X|  
|Windows Phone 8.0|||X|X|  
|Android|||X|X|  
|iOS|||X|X|  
  
## 컴파일러  
  
|컴파일러|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional\/Community|Visual Studio Enterprise|  
|----------|---------------------------------------|-----------------------------------------------|-------------------------------------------|------------------------------|  
|32비트 x86 컴파일러|X|X|X|X|  
|X86\_arm 크로스 컴파일러|X||X|X|  
|64비트 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 컴파일러|||X|X|  
|X86\_ [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 크로스 컴파일러|X|X|X|X|  
  
## 라이브러리 및 헤더  
  
|라이브러리 또는 헤더|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional\/Community|Visual Studio Enterprise|  
|-----------------|---------------------------------------|-----------------------------------------------|-------------------------------------------|------------------------------|  
|Windows 헤더, 라이브러리 및 CRT 라이브러리|\(X\)|X|X|X|  
|STL|X|X|X|X|  
|ATL|||X|X|  
|MFC|||X|X|  
|.NET Framework 클래스 라이브러리||X|X|X|  
|.NET용 C\+\+ 지원 라이브러리||X|X|X|  
|OpenMP|X|X|X|X|  
  
## 프로젝트 템플릿  
  
|템플릿|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional\/Community|Visual Studio Enterprise|  
|---------|---------------------------------------|-----------------------------------------------|-------------------------------------------|------------------------------|  
|UWP, Windows 8.1, Windows Phone 8.0용 XAML 템플릿|X||X|X|  
|Direct3D 응용 프로그램|X||X|X|  
|DLL\(Windows 스토어 앱\)|X||X|X|  
|정적 라이브러리\(Windows 스토어 앱\)|X||X|X|  
|Windows 런타임 구성 요소|X||X|X|  
|단위 테스트 라이브러리\(Windows 스토어 앱\)|X||X|X|  
|ATL 프로젝트|||X|X|  
|클래스 라이브러리\(CLR\)||X|X|X|  
|CLR 콘솔 응용 프로그램||X|X|X|  
|CLR 빈 프로젝트||X|X|X|  
|사용자 지정 마법사|||X|X|  
|빈 프로젝트||X|X|X|  
|메이크파일 프로젝트||X|X|X|  
|MFC ActiveX 컨트롤|||X|X|  
|MFC 응용 프로그램|||X|X|  
|MFC DLL|||X|X|  
|테스트 프로젝트|X|X|X|X|  
|Win32 콘솔 응용 프로그램||X|X|X|  
|Win32 프로젝트||X|X|X|  
  
## 도구  
  
|도구|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional\/Community|Visual Studio Enterprise|  
|--------|---------------------------------------|-----------------------------------------------|-------------------------------------------|------------------------------|  
|Incremental Linker\(Link.exe\)|X|X|X|X|  
|Program Maintenance Utility\(Nmake.exe\)||X|X|X|  
|Lib Generator\(Lib.exe\)|X|X|X|X|  
|Windows Resource Compiler\(Rc.exe\)|X|X|X|X|  
|Windows Resource to Object Converter\(CvtRes.exe\)||X|X|X|  
|Browse Information Maintenance Utility\(BscMake.exe\)|X|X|X|X|  
|C\+\+ Name Undecorator\(Undname.exe\)|X|X|X|X|  
|COFF\/PE Dumper\(Dumpbin.exe\)|X|X|X|X|  
|COFF\/PE Editor\(Editbin.exe\)|X|X|X|X|  
|MASM\(Ml.exe\)|||X|X|  
|Spy\+\+|||X|X|  
|ErrLook|||X|X|  
|AtlTrace|||X|X|  
|Devenv.com|||X|X|  
|유추 규칙|||X|X|  
|MSBuild에 VCBuild.vcproj 프로젝트 업그레이드\(VCUpgrade.exe\)|X|X|X|X|  
|프로필 기반 최적화|||X|X|  
  
## 디버깅 기능  
  
|디버깅 기능|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional\/Community|Visual Studio Enterprise|  
|------------|---------------------------------------|-----------------------------------------------|-------------------------------------------|------------------------------|  
|네이티브 디버깅|X|X|X|X|  
|natvis\(네이티브 형식 시각화\)|X|X|X|X|  
|그래픽 디버깅|X||X|X|  
|관리 디버깅||X|X|X|  
|GPU 사용량|X||X|X|  
|메모리 사용량|X||X|X|  
|원격 디버깅|X|X|X|X|  
|SQL 디버깅|||X|X|  
|정적 코드 분석|제한됨|제한됨|X|X|  
  
## 디자이너 및 편집기  
  
|디자이너 또는 편집기|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional\/Community|Visual Studio Enterprise|  
|-----------------|---------------------------------------|-----------------------------------------------|-------------------------------------------|------------------------------|  
|XAML 디자이너|X||X|X|  
|CSS 스타일 디자이너\/편집기|X|X|X|X|  
|HTML 디자이너\/편집기|X|X|X|X|  
|XML 편집기|X|X|X|X|  
|소스 코드 편집기|X|X|X|X|  
|생산성 기능: 리팩터링, IntelliSense, C\+\+ 코드 서식 지정|X|X|X|X|  
|Windows Forms 디자이너||X|X|X|  
|데이터 디자이너|||X|X|  
|네이티브 리소스 편집기\(.rc 파일\)|||X|X|  
|리소스 편집기|X|X|X|X|  
|모델 편집기|X||X|X|  
|셰이더 디자이너|X||X|X|  
  
## 데이터 기능  
  
|데이터 기능|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional\/Community|Visual Studio Premium|Visual Studio Enterprise|  
|------------|---------------------------------------|-----------------------------------------------|-------------------------------------------|---------------------------|------------------------------|  
|데이터 디자이너|||X|X|X|  
|데이터 개체|||X|X|X|  
|웹 서비스|||X|X|X|  
|서버 탐색기|||X|X|X|  
  
## 빌드 및 프로젝트 시스템  
  
|빌드 또는 프로젝트 기능|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional\/Community|Visual Studio Enterprise|  
|-------------------|---------------------------------------|-----------------------------------------------|-------------------------------------------|------------------------------|  
|명령줄 빌드\(msbuild.exe\)|X|X|X|X|  
|네이티브 다중 대상 지정||X|X|X|  
|관리되는 다중 대상 지정||X|X|X|  
|병렬 빌드|X|X|X|X|  
|빌드 사용자 지정|X|X|X|X|  
|속성 페이지 확장성|X|X|X|X|  
  
## 자동화 및 확장성  
  
|자동화 및 확장성|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional\/Community|Visual Studio Enterprise|  
|---------------|---------------------------------------|-----------------------------------------------|-------------------------------------------|------------------------------|  
|확장성 개체 모델|||X|X|  
|코드 모델|||X|X|  
|프로젝트 모델|||X|X|  
|리소스 편집기 모델|||X|X|  
|마법사 모델|||X|X|  
|디버거 개체 모델|||X|X|  
  
## Application Lifecycle Management 도구  
  
||||||  
|-|-|-|-|-|  
|도구|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional\/Community|Visual Studio Enterprise|  
|단위 테스트\(네이티브 프레임워크\)|X|X|X|X|  
|단위 테스트\(관리되는 프레임워크\)||X|X|X|  
|코드 검사||||X|  
|수동 테스트||||X|  
|예비 테스트||||X|  
|테스트 사례 관리||||X|  
|코드 맵 및 종속성 그래프|||읽기 전용|X|  
|코드 맵 디버깅||||X|  
  
## 참고 항목  
 [Visual Studio 설치](../Topic/Installing%20Visual%20Studio%202015.md)   
 [Visual Studio 2015의 새로운 기능](../Topic/What's%20New%20in%20Visual%20Studio%202015.md)   
 [Visual C\+\+ 프로젝트 형식](../ide/visual-cpp-project-types.md)   
 [Visual Database Tools 버전](http://msdn.microsoft.com/ko-kr/a7689adc-f16b-4cc7-b6fe-39ca0c711161)