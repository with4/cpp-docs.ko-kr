---
title: CLR을 대상으로 하는 c + + 프로그램 컴파일 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command-line applications [C++], managed code
- compiling programs [C++]
- Visual C++, managed code
- managed code [C++]
ms.assetid: 339f89df-a5d2-4040-831a-ddbe25b5dce4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2a7bcb0eead62730f0b70b0b1df64e5ed08f1f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-compiling-a-c-program-that-targets-the-clr-in-visual-studio"></a>연습: Visual Studio에서 CLR을 대상으로 하는 C++ 프로그램 컴파일
.NET 클래스를 사용 하 고 Visual Studio 개발 환경 사용 하 여 컴파일하는 Visual c + + 프로그램을 만들 수 있습니다.  
  
 이 절차에 대 한 Visual c + + 프로그램을 직접 입력할 수도 있고 샘플 프로그램 중 하나를 사용 하 여 키를 누릅니다. 이 절차에서 사용 하는 샘플 프로그램 textfile.txt 라는 텍스트 파일을 만들고 프로젝트 디렉터리에 저장 합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 각 항목들은 C++ 언어의 기본적인 사항을 이해하고 있다고 가정합니다.  
  
### <a name="to-create-a-new-project-in-visual-studio-and-add-a-new-source-file"></a>Visual Studio에서 새 프로젝트를 만들고 새 소스 파일을 추가 하려면  
  
1.  새 프로젝트를 만듭니다. **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
2.  Visual c + + 프로젝트 형식에서 클릭 **CLR**, 클릭 하 고 **CLR 빈 프로젝트**합니다.  
  
3.  프로젝트 이름을 입력 합니다.  
  
     기본적으로 프로젝트를 포함 하는 솔루션에 새 프로젝트와 동일한 이름이 되지만 다른 이름을 입력할 수 있습니다. 원하는 경우 프로젝트에 대 한 다른 위치를 입력할 수 있습니다.  
  
     클릭 **확인** 새 프로젝트를 만듭니다.  
  
4.  솔루션 탐색기가 표시 되지 않는 경우 클릭 **솔루션 탐색기** 에 **보기** 메뉴.  
  
5.  새 소스 파일을 프로젝트에 추가 합니다.  
  
    -   마우스 오른쪽 단추로 클릭는 **소스 파일** 폴더 솔루션 탐색기에서 가리키고 **추가** 클릭 **새 항목**합니다.  
  
    -   클릭 **c + + 파일 (.cpp)** 파일 이름을 입력 하 고 클릭 **추가**합니다.  
  
     **.cpp** 에 파일이 표시는 **소스 파일** 탭된 창 및 솔루션 탐색기의 폴더에 나타납니다 해당 파일에 원하는 합니다.  
  
6.  Visual Studio에서 새로 만든된 탭 클릭 하 고 유효한 Visual c + + 프로그램을 입력 하거나 복사 한 샘플 프로그램 중 하나를 붙여 합니다.  
  
     예를 들어, 사용할 수는 [하는 방법: 텍스트 파일 쓰기 (C + + /cli CLI)](../dotnet/how-to-write-a-text-file-cpp-cli.md) 샘플 프로그램 (에 **파일 처리 및 I/O** 프로그래밍 가이드의 노드).  
  
     사용 하는 샘플 프로그램을 사용 하는 경우 발생할는 `gcnew` 키워드 대신 `new` .NET 개체를 만들 때 `gcnew` 핸들 반환 (`^`) 포인터 대신 (`*`):  
  
     `StreamWriter^ sw = gcnew StreamWriter(fileName);`  
  
     새 Visual c + + 구문에 대 한 자세한 내용은 참조 하십시오. [런타임 플랫폼용 구성 요소 확장명](../windows/component-extensions-for-runtime-platforms.md)합니다.  
  
7.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     **출력** 창 빌드 상태를 나타내는 메시지는 빌드 로그의 위치와 같은 컴파일 진행 상황에 대 한 정보를 표시 합니다.  
  
     변경 하 고 빌드 작업을 수행 하지 않고 프로그램을 실행 하는 경우 대화 상자는 프로젝트는 만료를 나타낼 수 있습니다. 클릭 하기 전에이 대화 상자에서 확인란을 선택 **확인** 빌드할 때마다 메시지를 표시 하는 대신 항상 최신 버전의 파일을 사용 하도록 Visual Studio에 들어 있습니다.  
  
8.  **디버그** 메뉴를 클릭하여 **디버깅하지 않고 시작**을 선택합니다.  
  
9. 프로그램을 실행할 때 샘플 프로그램을 사용한 텍스트 파일이 만들어졌는지 여부를 나타내는 명령 창을 표시 됩니다. 명령 창을 닫으려면 아무 키나를 누르십시오.  
  
     **textfile.txt** 텍스트 파일은 이제 프로젝트 디렉터리에 있습니다. 메모장을 사용 하 여이 파일을 열 수 있습니다.  
  
    > [!NOTE]
    >  빈 CLR 선택 프로젝트 템플릿이 자동으로 설정 된 **/clr** 컴파일러 옵션입니다. 프로젝트를 마우스 오른쪽 단추로 클릭이 확인 하려면 **솔루션 탐색기** 클릭 하 고 **속성**, 한 다음 확인은 **공용 언어 런타임 지원** 는 에서옵션 **일반** 의 노드 **구성 속성**합니다.  
  
## <a name="whats-next"></a>새로운 기능  
 **이전:** [연습: 명령줄에서 네이티브 c + + 프로그램 컴파일](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md) &#124; **다음:**[연습: 명령줄에서 C 프로그램 컴파일](../build/walkthrough-compile-a-c-program-on-the-command-line.md)  
  
## <a name="see-also"></a>참고 항목  
 [C++ 언어 참조](../cpp/cpp-language-reference.md)   
 [C/C++ 프로그램 빌드](../build/building-c-cpp-programs.md)