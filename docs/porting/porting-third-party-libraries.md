---
title: "타사 라이브러리 포팅 | Microsoft 문서"
ms.custom: 
ms.date: 01/10/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- 3rd-party libraries
- vspkg
ms.assetid: b055ed20-8a9e-45b2-ac2a-e3d94271c009
caps.latest.revision: 0
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 8630a5c0b97b85e0dc75e8b470974bb7d223a511
ms.openlocfilehash: 1d85010b6068d52d8522875a3c47561ad777d345
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---

# <a name="porting-third-party-libraries"></a>타사 라이브러리 포팅

현재 버전의 Visual C++로 프로젝트를 업그레이드하는 경우 프로젝트에 사용되는 모든 라이브러리도 업그레이드하여 라이브러리와 프로젝트가 동일한 버전과 특성의 컴파일러로 빌드되도록 해야 합니다. 자세한 내용은 [잠재적인 업그레이드 문제 개요](overview-of-potential-upgrade-issues-visual-cpp.md)를 참조하세요. 

## <a name="introducing-vcpkg"></a>vcpkg 소개
과거에는 타사 라이브러리를 찾고 업그레이드하는 것이 그리 쉬운 작업이 아니었습니다. 타사의 C++ 오픈 소스 라이브러리를 얻고 다시 빌드하기 쉽도록 Visual C++ 팀은 **VC++ 패키징 도구**, 즉 **vcpkg**라는 명령줄 도구를 만들었습니다. vcpkg에는 다양한 인기 C++ 오픈 소스 라이브러리의 검색 가능 카탈로그가 있습니다. vcpkg 명령줄에서 직접 카탈로그에 있는 모든 라이브러리를 설치할 수 있습니다. 라이브러리를 설치할 때 Vcpkg는 컴퓨터에 디렉터리 트리를 만들고 .h, .lib 및 이진 파일을 이 폴더에 추가합니다. 컴파일 명령줄에서 이 폴더를 사용하거나, vcpkg integrate install 명령을 사용하여 Visual Studio 2015 이상에 통합할 수 있습니다. 라이브러리 위치를 통합한 후에는 Visual Studio가 라이브러리를 찾고 생성되는 모든 새 프로젝트에 추가할 수 있습니다. 라이브러리를 사용하려는 경우 #include로 포함하기만 하면 Visual Studio가 프로젝트 설정에 대한 .lib 경로를 자동으로 추가하고 솔루션 폴더에 dll을 복사합니다.

## <a name="acquisition-and-usage"></a>획득 및 사용

[vcpkg GitHub 리포지토리][vcpkg](https://github.com/Microsoft/vcpkg/)에서 vcpkg를 다운로드할 수 있습니다.

 - 카탈로그에서 라이브러리를 검색하려면: vcpkg search <LibName>
 - 라이브러리(예: Boost)를 얻으려면: vcpkg install boost
 - 현재 설치된 라이브러리를 나열하려면: vcpkg list

블로그 게시물 [Vcpkg: a tool to acquire and build C++ open source libraries on Windows](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/)(Vcpkg: Windows에서 C++ 오픈 소스 라이브러리를 얻고 빌드하기 위한 도구)에서는 vcpkg의 작동 방식을 설명하고 지원되는 라이브러리 목록을 제공합니다. 목록은 매주 업데이트됩니다.

## <a name="reporting-issues"></a>문제 보고
vcpkg 카탈로그에 해당 라이브러리가 없는 경우 [GitHub 리포지토리](https://github.com/Microsoft/vcpkg/issues)에서 문제를 열 수 있습니다. 커뮤니티 및 Visual C++ 팀은 여기서 문제를 확인하고 이 라이브러리에 대한 포트 파일을 만들 수 있습니다.

전용 타사 라이브러리(비오픈 소스)의 경우 라이브러리 공급자에게 문의하는 것이 좋습니다. 그러나 사용 중이거나 사용자를 차단하는 전용 라이브러리에 대해 알고 싶으니 어떤 라이브러리를 사용하고 있는지 알려주세요. vcupgrade@microsoft.com으로 연락하시면 됩니다.

  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 포팅 및 업그레이드 가이드](visual-cpp-porting-and-upgrading-guide.md)

