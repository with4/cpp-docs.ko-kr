---
title: Dll의 종류 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC DLLs [C++], types
- DLLs [C++], types
- DLLs [C++], MFC
ms.assetid: f6a30db9-6138-4b2c-90cc-a17855e499a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 605d60535df8d0a94d58e120df89f975402b8a22
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369944"
---
# <a name="kinds-of-dlls"></a>DLL 종류
이 항목에서는 작성 하는 DLL의 종류를 결정 하는 데 유용한 정보를 제공 합니다.  
  
##  <a name="_core_the_different_kinds_of_dlls_available_with_visual_c.2b2b"></a> 다른 종류의 사용 가능한 Dll  
 Visual c + +를 사용 하 여 Microsoft Foundation 클래스 (MFC) 라이브러리를 사용 하지 않는 C 또는 c + +에서 Win32 Dll을 빌드할 수 있습니다. Win32 응용 프로그램 마법사로 비 MFC DLL 프로젝트를 만들 수 있습니다.  
  
 MFC 라이브러리 자체는 여러 MFC DLL 마법사로 Dll 또는 정적 연결 라이브러리 중 하나에 사용할 수 있습니다. DLL에서 MFC를 사용 중인 경우 Visual c + + 3 가지 다른 DLL 개발 시나리오를 지원 합니다.  
  
-   일반 MFC DLL에 세울 정적으로 MFC에 연결  
  
-   MFC를 연결 하는 일반적인 MFC DLL를 동적으로 작성  
  
-   MFC 확장 DLL을 작성 하는 항상 동적으로 연결 MFC  
  
### <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [비 MFC DLL: 개요](../build/non-mfc-dlls-overview.md)  
  
-   [기본 MFC Dll에 정적으로 MFC에 링크](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [동적으로 MFC에 링크 하는 기본 MFC Dll](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC 확장명 DLL: 개요](../build/extension-dlls-overview.md)  
  
-   [사용 하는 DLL의 종류](#_core_which_kind_of_dll_to_use)  
  
##  <a name="_core_which_kind_of_dll_to_use"></a> 사용 하 여 DLL의 종류를 결정합니다.  
 DLL에서 MFC를 사용 하지 않는 Visual c + +를 사용 하 여 비 MFC Win32 DLL을 빌드합니다. 메모리 및 디스크 공간을 많이 차지 (정적 또는 동적으로)을 MFC DLL을 링크 합니다. DLL이 MFC 실제로 사용 하지 않는 한 MFC에 링크 하지 말아야 합니다.  
  
 DLL MFC를 사용 하는 MFC 또는 비 MFC 응용 프로그램에서 사용할 경우 동적으로 MFC에 링크 하는 MFC 기본 DLL 또는 정적으로 MFC에 링크 하는 MFC 기본 DLL 빌드해야 합니다. 대부분의 경우에서 동적으로 MFC에 링크 하는 DLL의 파일 크기는 훨씬 더 작은 되 고 공유 버전의 MFC 사용 하 여 메모리에 공간 절약에 대해서는 중요할 수 있습니다는 MFC 기본 DLL를 사용 하려고 할 합니다. MFC에 정적으로 링크 하는 경우 DLL의 파일 크기 보다 큰 되며 MFC 라이브러리 코드의 개인 복사본이 로드 때문에 잠재적으로 추가 메모리를 차지 합니다.  
  
 동적으로 MFC에 링크는 한 dll은 MFC를 직접 연결할 필요가 없기 때문에 정적으로 MFC에 링크는 DLL을 빌드하는 것 보다 더 빠르게 합니다. 디버그 빌드 링커 디버그 정보를 압축 해야에 특히 유용 합니다. 디버그 정보가 이미 들어 있는 DLL을 연결 하 여 DLL 내에서 압축에 디버그 정보가 적게 포함 되어 있습니다.  
  
 동적으로 MFC에 링크 되는 한 가지 단점은 DLL를 공유 Dll Mfcx0.dll 및 Msvcrxx.dll (또는 유사한 파일) 배포 해야 합니다. MFC Dll은 자유롭게 재배포할 되지만 여전히 항상 설치 프로그램에서 Dll를 설치 해야 합니다. 또한 프로그램와 MFC Dll 자체 둘 다에서 사용 되는 C 런타임 라이브러리를 포함 하는 Msvcrxx.dll를 배송 해야 합니다.  
  
 DLL, MFC 실행 파일만 사용 하는 경우 기본 MFC DLL 또는 MFC 확장 DLL 작성 중 하나를 선택을 해야 합니다. DLL 기존 MFC 클래스에서 파생 된 다시 사용할 수 있는 클래스를 구현 하는 응용 프로그램과 DLL 사이의 MFC 파생 개체를 전달 해야 할 경우에 MFC 확장 DLL 빌드해야 합니다.  
  
 DLL은 동적으로 MFC에 링크를 경우 MFC Dll DLL 함께 재배포할 수 있습니다. 이 아키텍처는 디스크 공간을 절약 하 고 메모리 사용을 최소화 하는 여러 실행 파일 간에 클래스 라이브러리를 공유 하는 데 특히 유용 합니다.  
  
 4.0, Visual c + +만 지원 되는 두 종류의 MFC를 사용 하는 Dll 버전 이전의: USRDLLs 및 AFXDLLs 합니다. 기본 MFC Dll에 정적으로 MFC에 링크 된 이전 USRDLL으로 동일한 특징을 갖습니다. MFC 확장 Dll로 이전 AFXDLLs 동일한 특징을 갖습니다.  
  
### <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [비 MFC DLL: 개요](../build/non-mfc-dlls-overview.md)  
  
-   [기본 MFC Dll에 정적으로 MFC에 링크](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [동적으로 MFC에 링크 하는 기본 MFC Dll](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC 확장명 DLL: 개요](../build/extension-dlls-overview.md)  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++의 DLL](../build/dlls-in-visual-cpp.md)