---
title: '연습: 표준 C++ 프로그램(C++) 만들기 | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vcfirstapp
- vccreatefirst
dev_langs:
- C++
helpviewer_keywords:
- command-line applications [C++], standard
- standard applications [C++]
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4f3f01ab95237a0401394d429443804ce65a4385
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017330"
---
# <a name="walkthrough-creating-a-standard-c-program-c"></a>연습: 표준 C++ 프로그램(C++) 만들기
표준 C++ 프로그램을 만들어 Visual Studio 통합 개발 환경(IDE)에서 Visual C++를 사용할 수 있습니다. 이 연습 단계를 수행하면 Visual Studio에서 프로젝트를 만들고, 만든 프로젝트에 파일을 추가하며 C++ 코드를 추가하고 컴파일 및 실행까지 일련의 과정을 수행할 수 있습니다[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
 C++ 프로그램을 직접 입력하거나 샘플 프로그램 중 하나를 이용할 수 있습니다. 이 연습에서는 샘플 프로그램은 콘솔 응용 프로그램입니다. 이 응용 프로그램에서는 C++ 표준 라이브러리 컨테이너 `set`을 사용합니다.  
  
 Visual C++는 2003년에 제정된 C++ 표준대로 2단계 이름 조회, 예외 사양 및 내보내기와 같은 주요 변경대로 컴파일합니다. 또한 Visual C++ 람다 식, auto, static_assert, rvalue 참조 및 extern template과 같은 몇 가지 C++ 0x 기능을 지원합니다.  
  
> [!NOTE]
>  사용 하 여 표준 준수가 필요한 경우를 `/Za` 컴파일러 옵션을 표준 Microsoft 확장을 사용 하지 않도록 설정 합니다. 자세한 내용은 [/Za, /Ze (언어 확장명 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md)합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 C++ 언어의 기본적인 사항을 알고 있어야 합니다.  
  
### <a name="to-create-a-project-and-add-a-source-file"></a>프로젝트를 만들고 소스 파일을 추가 하려면  
  
1.  메뉴의 **파일**에서 **새로만들기**를 클릭한 다음 **프로젝트**를 선택하여 새 프로젝트를 만듭니다.  
  
2.  에 **Visual c + +** 프로젝트 형식 창에서 클릭 **Windows Desktop**를 클릭 하 고 **Windows 콘솔 응용 프로그램**.  
  
3.  프로젝트 이름을 입력합니다.   
  
     기본적으로 프로젝트를 포함하는 솔루션에 프로젝트와 동일한 이름이 허용되지만 다른 이름을 입력하는 것을 권장합니다. 프로젝트 위치를 변경할 수 있습니다.  
  
     **확인**을 클릭해 프로젝트를 만듭니다.  
  
4.  **솔루션 탐색기**가 표시되지 않는 경우 메뉴의 **보기**에서 **솔루션 탐색기**를 선택할 수 있습니다.  
  
5.  다음과 같이 새 소스 파일을 프로젝트에 추가 합니다.  
  
    1.  **솔루션 탐색기**에서 **소스 파일** 폴더를 마우스 오른쪽 단추로 클릭하고 **추가**를 클릭 후 **새 항목**을 선택합니다.  
  
    2.  **코드** 노드에서 **C++ 파일(.cpp)** 을 클릭하고, 파일 이름을 입력한 다음 **추가**를 클릭합니다.  
  
     .Cpp 파일이 합니다 **소스 파일** 폴더에서 **솔루션 탐색기**, 파일을 Visual Studio 편집기에서 연 합니다.  
  
6.  편집기의 파일에서 C++ 표준 라이브러리를 사용하는 올바른 C++ 프로그램 입력 샘플 프로그램 중 하나를 복사하여 파일에 붙여넣습니다.
  
  
7.  파일을 저장합니다.  
  
8. **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     **출력** 창에서는 빌드 로그 및 빌드 상태를 나타내는 메시지와 같은 컴파일 진행 상황을 안내합니다.  
  
9. **디버그** 메뉴를 클릭하여 **디버깅하지 않고 시작**을 선택합니다.  
  
     샘플 프로그램을 사용하는 경우 명령 창이 표시되고 `set`에서 특정 정수를 찾았는지를 보여줍니다.  
  
## <a name="next-steps"></a>다음 단계  
 **이전:** [콘솔 Visual C++에서 응용 프로그램](../windows/console-applications-in-visual-cpp.md)합니다. **다음:**[연습: 명령줄에서 네이티브 C++ 프로그램 컴파일](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)합니다.
  
## <a name="see-also"></a>참고 항목  
 [C++ 언어 참조](../cpp/cpp-language-reference.md)   
 [C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)