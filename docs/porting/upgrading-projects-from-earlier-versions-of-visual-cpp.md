---
title: 이전 버전의 Visual C++에서 프로젝트 업그레이드 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- 32-bit code porting
- upgrading Visual C++ applications, 32-bit code
ms.assetid: 18cdacaa-4742-43db-9e4c-2d9e73d8cc84
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c503a2feae728c67507bf80db6eb2c5dabc3252f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849732"
---
# <a name="upgrading-projects-from-earlier-versions-of-visual-c"></a>이전 버전의 Visual C++에서 프로젝트 업그레이드
대부분의 경우 Visual Studio 이전 버전에서 만든 프로젝트를 열 수 있습니다. 그러나 이를 위해 Visual Studio는 프로젝트를 업그레이드합니다. 이 업그레이드된 프로젝트를 저장하면 이전 버전에서 열 수 없습니다.  
  
> [!IMPORTANT]
>  이미 변환된 프로젝트를 변환하려는 경우 재변환을 하면 기존 파일이 삭제되므로 Visual Studio가 확인을 요청합니다.  
  
 업그레이드된 여러 프로젝트 및 솔루션은 수정 없이 성공적으로 빌드할 수 있습니다. 그러나 일부 프로젝트의 경우 설정, 소스 코드 또는 양쪽을 변경해야 합니다. 다음 지침을 사용하여 설정 문제를 먼저 해결하는 것이 좋으며 그래도 프로젝트가 빌드되지 않으면 코드 문제를 해결할 수 있습니다. 자세한 내용은 [잠재적인 업그레이드 문제 개요](../porting/overview-of-potential-upgrade-issues-visual-cpp.md)를 참조하세요.  
  
1.  기존 프로젝트 및 솔루션 파일의 복사본을 만듭니다. 원할 경우 파일 버전을 비교할 수 있도록 Visual Studio의 현재 버전과 이전 버전을 함께 설치합니다.  
  
2.  현재 버전의 Visual Studio에서 프로젝트 또는 솔루션의 복사본을 열어 업데이트하고 저장합니다.  
  
3.  변환된 각 프로젝트에 대해 바로 가기 메뉴를 열고 **속성**을 선택합니다. **구성 속성**에서 **일반** 을 선택한 다음 **플랫폼 도구 집합**에 대해 현재 버전을 선택합니다. 예를 들어 Visual Studio 2017의 경우 v141을 선택합니다.  
  
4.  솔루션을 빌드합니다. 빌드가 실패하면 설정을 수정하고 다시 빌드합니다.  
  
 그 소스에서 저장된 절차를 더 쉽게 수정 및 디버깅할 수 있도록 데이터 소스는 별도의 데이터베이스 프로젝트에 포함되어 있습니다. 데이터 소스가 포함된 C++ 프로젝트를 업그레이드하면 별도의 데이터베이스 프로젝트가 자동으로 만들어집니다.  
  
 대상 Windows 버전을 업데이트하는 방법에 대한 자세한 내용은 [WINVER 및 _WIN32_WINNT 수정](../porting/modifying-winver-and-win32-winnt.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [빌드 시스템 변경 내용](../build/build-system-changes.md)  
 [Visual Studio 2017의 Visual C++에 대한 새로운 기능](../what-s-new-for-visual-cpp-in-visual-studio.md) [Visual C++ 변경 기록 2003 - 2015](../porting/visual-cpp-change-history-2003-2015.md)   
 [비표준 동작](../cpp/nonstandard-behavior.md)