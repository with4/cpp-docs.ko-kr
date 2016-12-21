---
title: "연습: Win32 콘솔 프로그램 만들기(C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
f1_keywords: 
  - "vcfirstapp"
  - "vccreatefirst"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "명령줄 응용 프로그램[C++], 표준"
  - "독립형 응용 프로그램[C++]"
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
caps.latest.revision: 36
caps.handback.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연습: Win32 콘솔 프로그램 만들기(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio IDE\(통합 개발 환경\)에서 Visual C\+\+를 사용하여 표준 C\+\+ 프로그램을 만들 수 있습니다.  이 연습의 단계를 따르면 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]를 사용하여 프로젝트를 만들고 프로젝트에 새 파일을 추가한 다음 파일을 수정하여 C\+\+ 코드를 추가하고 프로그램을 컴파일 및 실행할 수 있습니다.  
  
 C\+\+ 프로그램을 직접 작성하거나 샘플 프로그램 중 하나를 사용할 수 있습니다.  이 연습의 샘플 프로그램은 콘솔 응용 프로그램입니다.  이 응용 프로그램은 STL\(표준 템플릿 라이브러리\)에서 `set` 컨테이너를 사용합니다.  
  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]는 2003 C\+\+ 표준을 따르지만 2단계 이름 조회, 예외 사양 및 내보내기라는 주요 예외가 있습니다.  또한 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]는 람다, auto, static\_assert, rvalue 참조 및 extern 템플릿과 같은 몇 가지 C\+\+0x 기능을 지원합니다.  
  
> [!NOTE]
>  표준을 따라야 하는 경우 **\/Za** 컴파일러 옵션을 사용하여 Microsoft의 표준 확장을 사용하지 않도록 설정합니다.  자세한 내용은 [\/Za, \/Ze\(언어 확장 사용 안 함\)](../build/reference/za-ze-disable-language-extensions.md)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 C\+\+ 언어의 기본적인 사항을 알고 있어야 합니다.  
  
### 프로젝트를 만들고 소스 파일을 추가하려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭하여 프로젝트를 만듭니다.  
  
2.  **Visual C\+\+** 프로젝트 형식 창에서 **Win32**를 클릭한 다음 **Win32 콘솔 응용 프로그램**을 클릭합니다.  
  
3.  프로젝트의 이름을 입력합니다.  
  
     프로젝트가 포함된 솔루션의 이름은 기본적으로 프로젝트의 이름과 동일하지만 사용자가 직접 다른 이름을 입력할 수 있습니다.  프로젝트의 다른 위치를 입력할 수도 있습니다.  
  
     **확인**을 클릭하여 프로젝트를 만듭니다.  
  
4.  **Win32 응용 프로그램 마법사**에서 **다음**을 클릭하고 **빈 프로젝트**를 선택한 다음 **마침**을 클릭합니다.  
  
5.  **솔루션 탐색기**가 표시되지 않으면 **보기** 메뉴에서 **솔루션 탐색기**를 클릭합니다.  
  
6.  다음과 같이 새 소스 파일을 프로젝트에 추가합니다.  
  
    1.  **솔루션 탐색기**에서 **소스 파일** 폴더를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **새 항목**을 클릭합니다.  
  
    2.  **코드** 노드에서 **C\+\+ 파일 \(.cpp\)**을 클릭하고 파일 이름을 입력한 다음 **추가**를 클릭합니다.  
  
     .cpp 파일이 **솔루션 탐색기**의 소스 파일 폴더에 나타나고 Visual Studio 편집기에서 열립니다.  
  
7.  편집기의 파일에서 표준 C\+\+ 라이브러리를 사용하는 올바른 C\+\+ 프로그램을 입력하거나 샘플 프로그램 중 하나를 복사하여 파일에 붙여 넣습니다.  
  
     예를 들어, 도움말에 포함된 표준 템플릿 라이브러리 샘플 중 하나인 [set::find](../misc/set-find-stl-samples.md) 샘플 프로그램을 사용할 수 있습니다.  
  
     샘플 프로그램을 사용하는 경우 `using namespace std;` 지시문에 주목할 필요가 있습니다.  이 지시문을 사용하면 프로그램에서 정규화된 이름\(`std::cout` 및 `std::endl`\) 대신 `cout` 및 `endl`을 사용할 수 있습니다.  
  
8.  파일을 저장합니다.  
  
9. **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     빌드 로그의 위치, 빌드 상태를 나타내는 메시지 등의 컴파일 진행 상황 정보가 **출력** 창에 표시됩니다.  
  
10. **디버그** 메뉴에서 **디버깅하지 않고 시작**을 클릭합니다.  
  
     샘플 프로그램을 사용한 경우 집합에서 특정 정수를 찾았는지 표시하는 명령 창이 나타납니다.  
  
## 다음 단계  
 **이전:** [Creating Command\-Line Applications \(C\+\+\)](http://msdn.microsoft.com/ko-kr/2505d9ed-aca4-426a-9071-078a2d707254) **다음:** [연습: 명령줄에서 네이티브 C\+\+ 프로그램 컴파일](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)  
  
## 참고 항목  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/ko-kr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [C\+\+ 언어 참조](../cpp/cpp-language-reference.md)   
 [C\+\+ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)