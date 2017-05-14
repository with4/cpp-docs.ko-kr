---
title: "링커 도구 오류 LNK1104 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1104
dev_langs:
- C++
helpviewer_keywords:
- LNK1104
ms.assetid: 9ca6f929-0efc-4055-8354-3cf5b4e636dc
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: c6121f598bc2913b65fe781b07bcc27e6b55375b
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

---
# <a name="linker-tools-error-lnk1104"></a>링커 도구 오류 LNK1104
파일을 열 수 없습니다 '*filename*'  
  
링커 지정된 된 파일을 열 수 없습니다.  
  
## <a name="possible-causes-and-solutions"></a>가능한 원인 및 해결
  
이 오류는 링커에서 읽기 또는 쓰기 위해 파일을 열려고 할 때 발생할 수 있습니다. 이 문제의 가장 일반적인 원인은 파일이 존재 하지 않는에 없는 디렉터리 중 하나는 링커는 검색, 또는 사용 하 고 다른 프로세스에 의해 잠겨 있습니다. 드물지만, 디스크 공간이 부족 해질 있을 수 있습니다, 파일이 너무 클 수, 파일 경로가 너무 길거나, 수 있습니다 또는 파일에 액세스할 수 있는 권한이 없을 수 있습니다.  

이러한 일반적인 문제 중 하나를 확인 합니다.  

-   다시 작성 하려고 할 때 응용 프로그램 실행 중입니다. 실행 파일 또는.pdb 같은 디버그 파일을 열 수 없는 파일 경우 이것이 일반적인 원인입니다. 이 문제를 해결 하려면 프로그램을 중지 하 고 다시 작성 하기 전에 디버거에서 언로드하십시오.  
  
-   파일 *filename* 은 솔루션에 의해 빌드 되지만 링커 액세스 하려고 할 때 아직 존재 하지 않습니다. 이 프로젝트 하 나와이 파일을 생성 하 고 다른 프로젝트에 따라 달라 집니다 하지만 프로젝트가 올바른 순서로 빌드되지 않은 경우 발생할 수 있습니다. 이 문제를 해결 하려면 프로젝트 참조를 요구 하기 전 누락 된 파일을 빌드할 하므로 파일을 사용 하는 프로젝트에 설정 되어 있는지를 확인 합니다. 자세한 내용은 참조 [Visual c + + 프로젝트에서 참조 추가](../../ide/adding-references-in-visual-cpp-projects.md) 및 [프로젝트의 참조 관리](/visualstudio/ide/managing-references-in-a-project)합니다.  
  
-   파일 이름 또는 명령줄에서 또는 #pragma lib 지시문에 지정 된 경로가 올바르지 않거나 경로 잘못 된 드라이브 지정 합니다. 맞춤법을 확인 하 고 지정된 된 위치에 파일이 있는지 확인 합니다.  
  
-   Visual Studio IDE를 다른 컴퓨터에서 복사 된 프로젝트를 빌드하려면 사용 하는 경우 라이브러리에 대 한 설치 위치는 달라질 수 있습니다. 라이브러리 디렉터리 속성을 확인 하십시오.는 [VC + + 디렉터리 속성 페이지](../../ide/vcpp-directories-property-page.md) 하 고 필요에 따라 업데이트 합니다. 보고 편집할 IDE에서 설정 합니다. 현재 라이브러리 경로 라이브러리 디렉터리 속성에 대 한 드롭다운 컨트롤을 선택 하 고 선택 **편집**합니다. **값 평가** 라이브러리 디렉터리 대화 상자의 섹션 라이브러리 파일의 검색 하는 현재 경로 나열 합니다.  
  
-   이전 버전의 Visual Studio를 사용 하 여 만든 프로젝트를 작성 하는 경우 플랫폼 도구 집합 및 해당 버전에 대 한 라이브러리 수 하지 설치할 수 없습니다. 이 문제를 해결 하려면 두 가지 옵션이 있습니다: 설치한 현재 플랫폼 도구 집합을 사용 하도록 프로젝트를 업그레이드할 수 있습니다 또는 이전 도구 집합을 설치 하 고 변경 하지 않고 프로젝트를 빌드할 수 있습니다. 자세한 내용은 참조 [프로젝트를 이전 버전의 Visual c + +에서에서 업그레이드할](../../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md) 및 [이전 프로젝트를 빌드하려면 Visual Studio의 네이티브 멀티 타기 팅을 사용](../../porting/use-native-multi-targeting.md)합니다.
  
-   현재 프로젝트 구성 또는 플랫폼 도구 집합에 대 한 라이브러리가 설치 되지 않습니다. 플랫폼 도구 집합 및 Windows SDK에 지정 있는지 확인은 [일반 속성 페이지](../../ide/general-property-page-project.md) 프로젝트에 대해 설치 되 고 필요한 라이브러리에 지정 된 라이브러리 디렉터리에서 사용할 수 있는지 확인은 [VC + + 디렉터리 속성 페이지](../../ide/vcpp-directories-property-page.md) 구성 설정에 대 한 합니다. 디버그 및 소매 구성에 대 한 별도 설정이 하나 빌드의 작동 하는 경우 오류가 발생 하면 다른 설정이 올바른지, 그리고 두 구성 모두에 대 한 설치 되는 필요한 도구 및 라이브러리에 있는지 확인 하므로 합니다.  
  
-   Windows SDK의 경로 만료 합니다. 버전의 Visual Studio 버전 보다 최신 버전인 Windows SDK의 버전을 설치한 경우에 지정 된 된 경로 있는지 확인은 [VC + + 디렉터리 속성 페이지](../../ide/vcpp-directories-property-page.md) 새 SDK와 일치 하도록 업데이트 됩니다. 개발자 명령 프롬프트를 사용 하는 경우 새 SDK 경로 대 한 환경 변수를 초기화 하는 일괄 처리 파일 업데이트 되었는지 확인 합니다.  
  
-   다른 프로그램에서 파일을 열어서 링커에서 해당 파일에 쓸 수 없습니다. 바이러스 백신 프로그램 종종 일시적으로 차단 새로 만든된 파일에 대 한 액세스. 이 문제를 해결 하려면 바이러스 백신 검사 프로그램에서 프로젝트 빌드 디렉터리를 제외 해 보십시오.  
  
-   병렬 빌드 옵션을 사용 하는 경우에 Visual Studio가 다른 스레드에서 파일을 잠금 가능 합니다. 이 문제를 해결 하려면 동일한 코드 개체 또는 여러 프로젝트에 라이브러리 작성 하지 마십시오 하 고 프로젝트에서 빌드된 이진 파일을 선택할 빌드 종속 항목 또는 프로젝트 참조를 사용을 확인 합니다.  
  
-   잘못 된 LIB 환경 변수를 만들어야합니다. 명령줄 빌드에 LIB 환경 변수 설정 하 고이 사용 하면 라이브러리에 대 한 모든 디렉터리를 포함 있는지를 확인 합니다. IDE에서 LIB 변수 속성으로 설정 된 라이브러리 디렉터리에는 [VC + + 디렉터리 속성 페이지](../../ide/vcpp-directories-property-page.md)합니다. 모든 있는지 확인 해야 하는 라이브러리를 포함 하는 디렉터리는 다음과 같습니다. 라이브러리 디렉터리를 입력 해야 할 경우 표준 라이브러리 디렉터리를 재정의 하는, 사용할 수 있습니다는 [/LIBPATH](../../build/reference/libpath-additional-libpath.md)) 명령줄 또는 프로젝트에 대 한 링커 속성 페이지에서 추가 라이브러리 디렉터리 속성 옵션입니다.  
  
-   프로젝트의 속성 페이지 대화 상자에서 개별 라이브러리를 지정할 때 라이브러리 이름은 쉼표가 아닌 공백을 사용 하 여 구분 되어야 합니다.  
  
-   에 대 한 경로 *filename* 최대 260 자가 하를 확장 합니다. 이름을 변경 하거나 필요한 파일의 경로를 단축 하는 데 필요한 경우 디렉터리 구조를 다시 정렬 합니다.  
  
-   파일이 너무 큽니다. 라이브러리 또는 개체 파일 두 개 이상의 크기가 gigabyte 32 비트 링커 문제가 발생할 수 있습니다. 이 문제에 대 한 가능한 수정 하는 64 비트 도구 집합을 사용 하는 것입니다. 명령줄에서이 작업을 수행 하는 방법에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 명령줄에서 64 비트 Visual c + + 도구를 사용 하도록 설정](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)합니다. IDE에서이 작업을 수행 하는 방법에 대 한 정보를 참조 하십시오. [64 비트 컴파일러 및 도구를 사용 하 여 MSBuild](../../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md#using-msbuild-to-build-your-project) 및 스택 오버플로이 게시물: [amd64 네이티브 도구 체인을 사용 하 여 Visual Studio를 설정 하는 방법을](http://stackoverflow.com/questions/19820718/how-to-make-visual-studio-use-the-native-amd64-toolchain/23793055)합니다.  
  
-   에 액세스 하려면 부족 한 파일 권한이 *filename*합니다. 이 보호 된 시스템 디렉터리의 파일을 라이브러리에 액세스 하거나 자신의 원래 사용 권한을 가진 다른 사용자가에서 복사 된 파일을 사용 하는 경우 발생할 수 있습니다 설정 합니다. 이 문제를 해결 하려면 파일을 쓰기 가능 프로젝트 디렉터리로 이동 합니다. 파일이 쓰기 가능한 디렉터리에 액세스할 수 없거나 사용 권한이 되지만 관리자 명령 프롬프트를 사용 하 고 takeown.exe 명령 파일의 소유권을 갖도록를 실행할 수 있습니다.  
  
-   디스크 공간이 필요가 없습니다. 링커는 여러 사례에서 임시 파일을 사용합니다. 충분 한 디스크 공간이 있는 경우에 매우 큰 링크 상당 부분 사용 하거나 사용 가능한 디스크 공간을 조각 수 있습니다. 사용 하는 것이 좋습니다는 [/OPT (최적화)](../../build/reference/opt-optimizations.md) 옵션; 수행 전이적 comdat 제거 읽기 모든 개체 파일 여러 번입니다.  
  
-   경우는 *filename* LNK 라는*n*, 임시 파일의 링커에 의해 생성 된 파일 이름인 TMP 환경 변수에 지정 된 디렉터리가 존재 하지 않을 수 있습니다, 또는 둘 이상의 디렉터리가 TMP 환경 변수에 대해 지정할 수 있습니다. TMP 환경 변수에 대해 하나의 디렉터리 경로만 지정 해야 합니다.  
  
-   라이브러리 이름에 대해 오류 메시지가 발생하고, 이전 Microsoft Visual C++ 개발 시스템에서 .mak 파일을 최근에 포팅한 경우 라이브러리가 더 이상 유효하지 않을 수 있습니다. 라이브러리 이름은 올바른 이며 지정된 된 위치에 있는지 확인 하거나 새 위치를 가리키도록 LIB 경로 업데이트 합니다.  

