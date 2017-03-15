---
title: "연습: Visual Studio에서 CLR을 대상으로 하는 C++ 프로그램 컴파일 | Microsoft Docs"
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
  - "명령줄 응용 프로그램[C++], 관리 코드"
  - "프로그램 컴파일[C++]"
  - "관리 코드[C++]"
  - "Visual C++, 관리 코드"
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
caps.latest.revision: 40
caps.handback.revision: 40
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 연습: Visual Studio에서 CLR을 대상으로 하는 C++ 프로그램 컴파일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

.NET 클래스를 사용하는 Visual C\+\+ 프로그램을 만든 다음 Visual Studio 개발 환경을 사용하여 이 프로그램을 컴파일할 수 있습니다.  
  
 이 절차에 사용할 Visual C\+\+ 프로그램을 직접 작성하거나 샘플 프로그램 중 하나를 사용할 수 있습니다.  이 절차에서 사용하는 샘플 프로그램에서는 textfile.txt라는 텍스트 파일을 만들고 이 파일을 프로젝트 디렉터리에 저장합니다.  
  
## 사전 요구 사항  
 이 항목에서는 사용자가 C\+\+ 언어의 기본적인 사항을 알고 있는 것으로 가정합니다.  
  
### Visual Studio에서 새 프로젝트를 만들고 새 소스 파일을 추가하려면  
  
1.  새 프로젝트를 만듭니다.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트...**를 클릭합니다.  
  
2.  Visual C\+\+ 프로젝트 형식에서 **CLR**을 클릭한 다음 **CLR 빈 프로젝트**를 클릭합니다.  
  
3.  프로젝트 이름을 입력합니다.  
  
     프로젝트가 포함된 솔루션의 이름은 기본적으로 새 프로젝트의 이름과 동일하지만 사용자가 직접 다른 이름을 입력할 수도 있습니다.  원하는 경우 프로젝트의 위치를 다른 곳으로 지정할 수 있습니다.  
  
     **확인**을 클릭하여 새 프로젝트를 만듭니다.  
  
4.  솔루션 탐색기가 열려 있지 않으면 **보기** 메뉴에서 **솔루션 탐색기**를 클릭합니다.  
  
5.  프로젝트에 새 소스 파일을 추가합니다.  
  
    -   솔루션 탐색기에서 **소스 파일** 폴더를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **새 항목...**을 클릭합니다.  
  
    -   **C\+\+ 파일\(.cpp\)**을 클릭하고 파일 이름을 입력한 다음 **추가**를 클릭합니다.  
  
     **.cpp** 파일이 솔루션 탐색기의 **소스 파일** 폴더와 탭 창에 나타납니다. 이 창에서 해당 파일에 필요한 코드를 입력할 수 있습니다.  
  
6.  Visual Studio에서 새로 만들어진 탭을 클릭하고 올바른 Visual C\+\+ 프로그램을 입력하거나 샘플 프로그램 중 하나를 복사하여 붙여넣습니다.  
  
     예를 들어, 프로그래밍 가이드의 **파일 처리 및 I\/O** 노드에 있는 [방법: 텍스트 파일 쓰기](../dotnet/how-to-write-a-text-file-cpp-cli.md) 샘플 프로그램을 사용할 수 있습니다.  
  
     샘플 프로그램을 사용하는 경우 .NET 개체를 만들 때 `new` 대신 `gcnew` `` 키워드를 사용하고, `gcnew`에서 포인터\(`*`\)가 아니라 핸들\(`^`\)을 반환합니다.  
  
     `StreamWriter^ sw = gcnew StreamWriter(fileName);`  
  
     새 Visual C\+\+ 구문에 대한 자세한 내용은 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)을 참조하십시오.  
  
7.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     **출력** 창에는 빌드 로그의 위치 및 빌드 상태를 나타내는 메시지 등의 컴파일 진행 상황 정보가 표시됩니다.  
  
     프로그램을 변경한 다음 빌드 작업을 수행하지 않고 프로그램을 실행하면 프로젝트가 최신 상태가 아님을 알리는 대화 상자가 나타날 수 있습니다.  빌드할 때마다 Visual Studio에서 해당 메시지를 표시하지 않고 항상 최신 버전의 파일을 사용하도록 하려면 **확인**을 클릭하기 전에 이 대화 상자의 확인란을 선택합니다.  
  
8.  **디버그** 메뉴에서 **디버깅하지 않고 시작**을 클릭합니다.  
  
9. 샘플 프로그램을 사용한 경우 프로그램을 실행하면 텍스트 파일을 만들었음을 나타내는 명령 창이 나타납니다.  임의의 키를 눌러 명령 창을 닫습니다.  
  
     **textfile.txt** 텍스트 파일이 프로젝트 디렉터리에 저장됩니다.  메모장을 사용하여 이 파일을 열 수 있습니다.  
  
    > [!NOTE]
    >  빈 CLR 프로젝트 템플릿을 선택하면 **\/clr** 컴파일러 옵션이 자동으로 설정됩니다.  이렇게 하려면 **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭한 다음 **구성 속성**의 **일반** 노드에 있는 **공용 언어 런타임 지원** 옵션을 선택합니다.  
  
## 새로운 기능  
 **이전:** [연습: 명령줄에서 네이티브 C\+\+ 프로그램 컴파일](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md) &#124; **다음:** [연습: 명령줄에서 C 프로그램 컴파일](../Topic/Walkthrough:%20Compiling%20a%20C%20Program%20on%20the%20Command%20Line.md)  
  
## 참고 항목  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/ko-kr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [C\+\+ 언어 참조](../cpp/cpp-language-reference.md)   
 [C\/C\+\+ 프로그램 빌드](../build/building-c-cpp-programs.md)