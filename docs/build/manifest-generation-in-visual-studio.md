---
title: Visual Studio에서 매니페스트 생성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
ms.assetid: 0af60aa9-d223-42cd-8426-b3fc543a2a81
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73b5cbe631d078dd6ee27b4f7e0a97503c36638b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="manifest-generation-in-visual-studio"></a>Visual Studio에서 매니페스트 생성
프로젝트의 특정 프로젝트에 대 한 매니페스트 파일의 생성을 제어할 수 있습니다 **속성 페이지** 대화 상자. 에 **구성 속성** 탭을 클릭 **링커**, 다음 **매니페스트 파일**, 다음 **매니페스트 생성**합니다. 기본적으로 새 프로젝트의 프로젝트 속성은 매니페스트 파일을 생성 하도록 설정 됩니다. 그러나 사용 하 여 프로젝트에 대 한 매니페스트 생성을 비활성화할 수는 **매니페스트 생성** 프로젝트의 속성입니다. 이 속성이로 설정 된 경우 **예**,이 프로젝트에 대 한 매니페스트가 생성 됩니다. 응용 프로그램 코드의 종속성을 확인할 때 링커가 어셈블리 정보를 무시 하는 그렇지 않으며 매니페스트를 생성 하지 않습니다.  
  
 Visual Studio의 빌드 시스템에서는 매니페스트를 최종 이진 응용 프로그램 파일에 포함 하거나 외부 파일로 생성 합니다. 이 동작에 의해 제어 되는 **매니페스트 포함** 옵션에 **프로젝트 속성** 대화 상자. 이 속성을 설정 하려면 엽니다는 **매니페스트 도구** 노드를 선택 합니다 **입력 및 출력**합니다. 매니페스트 포함 되지 않은 외부 파일로 생성 되어 최종 이진와 동일한 디렉터리에 저장 합니다. 매니페스트가 포함 된 경우 Visual Studio에서는 다음 프로세스를 사용 하 여 최종 매니페스트에서:  
  
1.  개체 파일에 소스 코드가 컴파일되면 링커 종속 어셈블리 정보를 수집 합니다. 링커는 최종 이진 파일을 연결 하는 동안 나중에 최종 매니페스트를 생성 하는 데 사용 되는 중간 매니페스트가 생성 합니다.  
  
2.  매니페스트 및 링크가 중간 완료 된 후 최종 매니페스트를 병합 하는 외부 파일로 저장 매니페스트 도구가 실행 됩니다.  
  
3.  프로젝트는 시스템을 작성 한 후 매니페스트 도구에 의해 생성 된 매니페스트가 이진 파일에 이미 포함 된 매니페스트가 보다 다른 정보가 포함 되어 있는지 여부를 검색 합니다.  
  
4.  이진에 포함 된 매니페스트, 매니페스트 도구에 의해 생성 된 매니페스트에서 다른 되었거나 이진에 포함 된 매니페스트가 없는 경우 Visual Studio는 호출 링커 한 번 더으로 이진 외부 매니페스트 파일을 포함 하는 리소스입니다.  
  
5.  이진에 포함 된 매니페스트 매니페스트 도구에 의해 생성 된 매니페스트와 동일한 경우 다음 빌드 단계에 빌드가 계속 됩니다.  
  
 매니페스트가 텍스트 리소스로 최종 이진에 포함 하 고 Visual Studio에서 파일로 최종 이진 파일을 열어 볼 수 있습니다. 매니페스트에 올바른 라이브러리를 가리키는지 하려면에 설명 된 단계를 따르십시오 [Visual c + + 응용 프로그램의 종속성 이해](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md) 에 설명 된 제안에 따라 또는 [문제해결](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md) 섹션.  
  
## <a name="see-also"></a>참고 항목  
 [방법: C/c + + 응용 프로그램에 매니페스트 포함](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md)   
 [전용 어셈블리에 대 한](http://msdn.microsoft.com/library/ff951638)   
 [매니페스트 도구](http://msdn.microsoft.com/library/aa375649)   
 [ 프로그램의 매니페스트 생성 이해](../build/understanding-manifest-generation-for-c-cpp-programs.md)