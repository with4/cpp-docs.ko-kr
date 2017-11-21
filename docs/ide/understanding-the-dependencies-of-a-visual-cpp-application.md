---
title: "Visual c + + 응용 프로그램의 종속성 이해 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- application deployment [C++], dependencies
- Dependency Walker
- dependencies [C++], application deployment and
- deploying applications [C++], dependencies
- DUMPBIN utility
- DLLs [C++], dependencies
- depends.exe
- libraries [C++], application deployment issues
ms.assetid: 62a44c95-c389-4c5f-82fd-07d7ef09dbf9
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 94e1978c5c0188410cf8d6d6bfdfe08d9af620e0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="understanding-the-dependencies-of-a-visual-c-application"></a>Visual C++ 응용 프로그램의 종속성 이해
응용 프로그램에 의존 하는 Visual c + + 라이브러리를 확인 하려면 프로젝트 속성을 볼 수 있습니다. (솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성** 열려는 **속성 페이지** 대화 상자.) 종속성을 더욱 포괄적으로 파악할 수 있는 Dependency Walker(depends.exe)를 사용할 수도 있습니다.  
  
 에 **속성 페이지** 대화 상자 아래에 있는 다양 한 페이지를 검사할 수 있습니다 **구성 속성** 종속성을 이해 하 합니다. 예를 들어, 프로젝트가 MFC 라이브러리를 사용 하 고 선택 하면 **MFC 사용**, **공유 DLL에서 MFC 사용** 에 **구성 속성**, **일반**  mfc와 같은 MFC Dll에 페이지 실행 시 응용 프로그램이 종속\<버전 >.dll입니다. 선택 하는 경우 CRT 라이브러리에 종속 수 응용 프로그램에서 MFC를 사용 하지 않는 경우는 **런타임 라이브러리** 값 **다중 스레드 디버그 DLL (/ MDd)** 또는 **다중 스레드 DLL (/ MD)**에 **구성 속성**, **C/c + +**, **코드 생성** 페이지.  
  
 응용 프로그램이 종속되는 DLL을 확인하는 더 포괄적인 방법은 Dependency Walker(depends.exe)를 사용하여 응용 프로그램을 여는 것입니다. 도구를 다운로드할 수 있습니다는 [Dependency Walker](http://go.microsoft.com/fwlink/p/?LinkId=132640) 웹 사이트입니다.  
  
 depends.exe를 사용하여 로드 시 응용 프로그램에 연결되는 DLL 목록과 지연 로드되는 DLL 목록을 확인할 수 있습니다. 런타임에 동적으로 로드되는 DLL의 전체 목록을 가져오려면 depends.exe의 프로파일링 기능을 사용하여 모든 코드 경로를 사용할 때까지 응용 프로그램을 테스트할 수 있습니다. 프로파일링 세션을 종료하면 depends.exe에서 런타임에 동적으로 로드된 DLL을 표시합니다.  
  
 depends.exe를 사용하여 종속성을 확인할 때 DLL이 다른 DLL이나 특정 DLL 버전에 대해 종속성을 가질 수도 있다는 점에 유의해야 합니다. depends.exe는 개발 컴퓨터 또는 대상 컴퓨터에서 사용할 수 있습니다. 개발 컴퓨터에서 depends.exe를 실행하면 응용 프로그램을 지원하는 데 필요한 DLL 목록이 표시됩니다. 대상 컴퓨터에서 실행할 응용 프로그램을 가져오는 데 문제가 있으면 depends.exe를 컴퓨터에 복사한 다음 도구에서 응용 프로그램을 열어 누락되거나 올바르지 않은 필수 DLL이 있는지 확인할 수 있습니다.  
  
 응용 프로그램이 종속된 DLL을 확인하면 응용 프로그램을 다른 컴퓨터에 배포할 때 이 응용 프로그램과 함께 재배포할 DLL을 이 목록 중에서 확인할 수 있습니다. 대부분의 경우에서 시스템 Dll은 재배포할 필요가 없습니다 되지만 Visual c + + 라이브러리에 대 한 Dll은 다시 배포 해야 할 수 있습니다. 자세한 내용은 참조 [재배포할 Dll 확인](../ide/determining-which-dlls-to-redistribute.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)