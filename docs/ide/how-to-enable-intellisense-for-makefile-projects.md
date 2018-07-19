---
title: '방법: 메이크파일 프로젝트에 IntelliSense 사용 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCNMakeTool.IntelliSense
dev_langs:
- C++
helpviewer_keywords:
- Makefile projects, IntelliSense
- IntelliSense, Makefile projects
ms.assetid: 9443f453-f18f-4f12-a9a1-ef9dbf8b188f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b9b11f04f1fe8d201d6d07ca5ed83f9ca7d991b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705464"
---
# <a name="how-to-enable-intellisense-for-makefile-projects"></a>방법: 메이크파일 프로젝트에 IntelliSense 사용
특정 프로젝트 설정 또는 컴파일러 옵션이 잘못 설정된 경우 Visual C++ 메이크파일 프로젝트용 IDE에서 IntelliSense가 작동하지 않습니다. 이 절차를 사용하여 Visual C++ 메이크파일 프로젝트를 구성하면 Visual Studio 개발 환경에서 메이크파일 프로젝트가 열려 있을 때 IntelliSense가 작동합니다.  
  
### <a name="to-enable-intellisense-for-makefile-projects-in-the-ide"></a>IDE에서 메이크파일 프로젝트에 IntelliSense를 사용하려면  
  
1.  **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [프로젝트 속성 작업](../ide/working-with-project-properties.md)을 참조하세요.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **NMake** 속성 페이지를 선택한 다음, **IntelliSense**에서 속성을 적절하게 수정합니다.  
  
    -   **전처리기 정의** 속성을 설정하여 메이크파일 프로젝트의 모든 전처리기 기호를 정의합니다. 자세한 내용은 [/D(전처리기 정의)](../build/reference/d-preprocessor-definitions.md)를 참조하세요.  
  
    -   **포함 검색 경로** 속성을 설정하여 컴파일러가 메이크파일 프로젝트의 전처리기 지시문에 전달되는 파일 참조를 확인하기 위해 검색할 디렉터리 목록을 지정합니다. 자세한 내용은 [/I(추가 포함 디렉터리)](../build/reference/i-additional-include-directories.md)를 참조하세요.  
  
         명령 창에서 CL.EXE를 사용하여 빌드된 프로젝트의 경우, **INCLUDE** 환경 변수를 설정하여 컴파일러가 메이크파일 프로젝트의 전처리기 지시문에 전달되는 파일 참조를 확인하기 위해 검색할 디렉터리를 지정합니다.  
  
    -   **강제 포함** 속성을 설정하여 메이크파일 프로젝트를 빌드할 때 처리할 헤더 파일을 지정합니다. 자세한 내용은 [/FI(강제 포함 파일 이름 지정)](../build/reference/fi-name-forced-include-file.md)를 참조하세요.  
  
    -   **어셈블리 검색 경로** 속성을 설정하여 프로젝트의 .NET 어셈블리에 대한 참조를 확인하기 위해 컴파일러에서 검색할 디렉터리 목록을 지정합니다. 자세한 내용은 [/AI(메타데이터 디렉터리 지정)](../build/reference/ai-specify-metadata-directories.md)를 참조하세요.  
  
    -   **강제 사용 어셈블리** 속성을 설정하여 메이크파일 프로젝트를 빌드할 때 처리할 .NET 어셈블리를 지정합니다. 자세한 내용은 [/FU(강제 #using 파일 이름 지정)](../build/reference/fu-name-forced-hash-using-file.md)를 참조하세요.  
  
    -   **추가 옵션** 속성을 설정하여 C++ 파일을 구문 분석할 때 IntelliSense에서 사용하는 추가 컴파일러 스위치를 지정합니다.  
  
4.  **확인**을 클릭하여 속성 페이지를 닫습니다.  
  
5.  **모두 저장** 명령을 사용하여 수정된 프로젝트 설정을 저장합니다.  
  
 다음에 Visual Studio 개발 환경에서 메이크파일 프로젝트를 열 때 메이크파일 프로젝트에서 **솔루션 정리** 명령을 실행한 다음, **솔루션 빌드** 명령을 실행합니다. IntelliSense는 IDE에서 제대로 작동해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IntelliSense 사용](/visualstudio/ide/using-intellisense)   
 [NMAKE 참조](../build/nmake-reference.md)   
 [방법: 기존 코드로 C++ 프로젝트 만들기](../ide/how-to-create-a-cpp-project-from-existing-code.md)