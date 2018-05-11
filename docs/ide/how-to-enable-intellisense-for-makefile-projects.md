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
ms.openlocfilehash: 9de79d56c6e8b6e496c0e7988ada07ed7595ea70
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enable-intellisense-for-makefile-projects"></a>방법: 메이크파일 프로젝트에 IntelliSense 사용
프로젝트 설정, 또는 컴파일러 옵션을 특정 하는 경우 Visual c + + 메이크파일 프로젝트에 대 한 IDE에서 작동 하기 위한 IntelliSense 실패는 잘못 설정 합니다. 메이크파일 프로젝트는 Visual Studio 개발 환경에서 열려 있는 경우 IntelliSense 작동 있도록이 절차를 사용 하 여 Visual c + + 메이크파일 프로젝트를 구성 합니다.  
  
### <a name="to-enable-intellisense-for-makefile-projects-in-the-ide"></a>IDE에서 메이크파일 프로젝트에 대 한 IntelliSense를 사용 하도록 설정 하려면  
  
1.  열기는 **속성 페이지** 대화 상자. 자세한 내용은 참조 [프로젝트 속성 작업](../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **구성 속성** 노드.  
  
3.  선택 된 **NMake** 속성 페이지를 선택한 다음 속성을 수정 **IntelliSense** 적절 하 게 합니다.  
  
    -   설정의 **전처리기 정의** 메이크파일 프로젝트의 모든 전처리기 기호를 정의 하는 속성입니다. 참조 [/D (전처리기 정의)](../build/reference/d-preprocessor-definitions.md), 자세한 정보에 대 한 합니다.  
  
    -   설정의 **포함 검색 경로** 속성을 통해 메이크파일 프로젝트의 전처리기 지시문에 전달 되는 파일 참조를 확인 하기 위해 컴파일러가 검색할 디렉터리 목록을 지정 합니다. 참조 [/I (추가 포함 디렉터리)](../build/reference/i-additional-include-directories.md), 자세한 정보에 대 한 합니다.  
  
         Cl 하는 프로젝트입니다. 명령 창에서 EXE를 설정의 **INCLUDE** 환경 변수 메이크파일 프로젝트의 전처리기 지시문에 전달 되는 파일 참조를 확인 하기 위해 컴파일러가 검색할 디렉터리를 지정 합니다.  
  
    -   설정의 **강제 포함** 속성을 통해 헤더 메이크파일 프로젝트를 빌드할 때 프로세스에 파일을 지정 합니다. 참조 [/FI (강제 포함 파일 이름)](../build/reference/fi-name-forced-include-file.md), 자세한 정보에 대 한 합니다.  
  
    -   설정의 **어셈블리 검색 경로** 속성을 통해 프로젝트에서.NET 어셈블리에 참조를 확인 하기 위해 컴파일러가 검색할 디렉터리 목록을 지정 합니다. 참조 [/AI (메타 데이터 디렉터리 지정)](../build/reference/ai-specify-metadata-directories.md), 자세한 정보에 대 한 합니다.  
  
    -   설정의 **강제 사용 어셈블리** 속성을 통해.NET 어셈블리 메이크파일 프로젝트를 빌드할 때 처리를 지정 합니다. 참조 [/FU (Name Forced #using 파일)](../build/reference/fu-name-forced-hash-using-file.md), 자세한 정보에 대 한 합니다.  
  
    -   설정의 **추가 옵션** 속성을 통해 c + + 파일을 구문 분석할 때 Intellisense에 사용할 추가 컴파일러 스위치를 지정 합니다.  
  
4.  클릭 **확인** 속성 페이지를 닫습니다.  
  
5.  사용 하 여는 **모두 저장** 수정된 된 프로젝트 설정을 저장 하는 명령입니다.  
  
 실행은 Visual Studio 개발 환경에서 메이크파일 프로젝트를 열 다음에 **솔루션 정리** 명령 차례로 **솔루션 빌드** 메이크파일 프로젝트에 명령 합니다. IntelliSense에서 IDE에서 제대로 작동 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IntelliSense 사용](/visualstudio/ide/using-intellisense)   
 [NMAKE 참조](../build/nmake-reference.md)   
 [방법: 기존 코드로 C++ 프로젝트 만들기](../ide/how-to-create-a-cpp-project-from-existing-code.md)