---
title: "방법: 메이크파일 프로젝트에 IntelliSense 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCNMakeTool.IntelliSense"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IntelliSense, 메이크파일 프로젝트"
  - "메이크파일 프로젝트, IntelliSense"
ms.assetid: 9443f453-f18f-4f12-a9a1-ef9dbf8b188f
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 메이크파일 프로젝트에 IntelliSense 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

특정 프로젝트 설정이나 컴파일러 옵션을 잘못 설정하면 IDE에서 Visual C\+\+ 메이크파일 프로젝트에 대해 IntelliSense가 작동하지 못합니다.  이 프로시저로 Visual C\+\+ 메이크파일 프로젝트를 구성하여 Visual Studio 개발 환경에서 메이크파일 프로젝트가 열릴 때 IntelliSense가 작동하도록 합니다.  
  
### IDE에서 메이크파일 프로젝트에 대해 IntelliSense를 활성화하려면  
  
1.  **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **NMake** 속성 페이지를 선택한 다음 **IntelliSense**에서 속성을 적절하게 수정합니다.  
  
    -   **전처리기 정의** 속성을 설정하여 메이크파일 프로젝트의 전처리기 기호를 모두 정의합니다.  자세한 내용은 [\/D\(전처리기 정의\)](../build/reference/d-preprocessor-definitions.md)를 참조하십시오.  
  
    -   **포함 검색 경로** 속성을 설정하여 메이크파일 프로젝트의 전처리기 지시문으로 전달되는 파일 참조를 확인하기 위해 컴파일러에서 검색할 디렉터리 목록을 지정합니다.  자세한 내용은 [\/I\(추가 포함 디렉터리\)](../build/reference/i-additional-include-directories.md)를 참조하십시오.  
  
         명령 창에서 CL.EXE를 사용하여 빌드된 프로젝트의 경우 **INCLUDE** 환경 변수를 설정하여 메이크파일 프로젝트의 전처리기 지시문으로 전달되는 파일 참조를 확인하기 위해 컴파일러가 검색할 디렉터리를 지정합니다.  
  
    -   **강제 포함** 속성을 설정하여 메이크파일 프로젝트를 빌드할 때 처리할 헤더 파일을 지정합니다.  자세한 내용은 [\/FI\(강제 포함 파일 이름 지정\)](../build/reference/fi-name-forced-include-file.md)를 참조하십시오.  
  
    -   **어셈블리 검색 경로** 속성을 설정하여 프로젝트에서 .NET 어셈블리에 대한 참조를 확인하기 위해 컴파일러가 검색할 디렉터리 목록을 지정합니다.  자세한 내용은 [\/AI\(메타데이터 디렉터리 지정\)](../build/reference/ai-specify-metadata-directories.md)를 참조하십시오.  
  
    -   **강제 사용 어셈블리** 속성을 설정하여 메이크파일 프로젝트를 빌드할 때 처리할 .NET 어셈블리를 지정합니다.  자세한 내용은 [\/FU\(강제 \#using 파일 이름 지정\)](../build/reference/fu-name-forced-hash-using-file.md)를 참조하십시오.  
  
    -   **추가 옵션** 속성을 설정하여 C\+\+ 파일을 구문 분석할 때 Intellisense에서 사용될 추가 컴파일러 스위치를 지정합니다.  
  
4.  **확인**을 클릭하여 속성 페이지를 닫습니다.  
  
5.  **모두 저장** 명령을 사용하여 수정된 프로젝트 설정을 저장합니다.  
  
 다음에 Visual Studio 개발 환경에서 메이크파일 프로젝트를 열 때, **솔루션 정리** 명령을 실행한 다음 메이크파일 프로젝트에 대해 **솔루션 빌드** 명령을 실행합니다.  그러면 IntelliSense가 IDE에서 제대로 작동합니다.  
  
## 참고 항목  
 [IntelliSense 사용](../Topic/Using%20IntelliSense.md)   
 [NMAKE 참조](../build/nmake-reference.md)   
 [방법: 기존 코드로 C\+\+ 프로젝트 만들기](../ide/how-to-create-a-cpp-project-from-existing-code.md)