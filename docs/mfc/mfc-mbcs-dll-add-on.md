---
title: "MFC MBCS DLL 추가 기능 | Microsoft Docs"
ms.custom: 
ms.date: 1/04/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MBCS
- MFC
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d6f134110ff95956cc37d6e038a680ff27cbc298
ms.sourcegitcommit: 56f6fce7d80e4f61d45752f4c8512e4ef0453e58
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2018
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL 추가 기능

MFC에 대 한 지원 및 멀티 바이트 문자 집합 (MBCS) 라이브러리의 Visual Studio 2015, 및 2017 Visual Studio 2013의 경우 설치 시는 추가 단계가 필요 합니다.

**Visual Studio 2013**: 기본적으로 Visual Studio 2013에 설치 된 MFC 라이브러리만 개발을 지 원하는 유니코드입니다. MBCS Dll에 Visual Studio 2013의 MFC 프로젝트를 빌드하기 위해 필요한는 **문자 집합** 속성이로 설정 **멀티 바이트 문자 집합 사용** 또는 **설정 하지**합니다. DLL에서 다운로드 [Visual Studio 2013 용 멀티 바이트 MFC 라이브러리](https://www.microsoft.com/en-us/download/details.aspx?id=40770)합니다.

**Visual Studio 2015**: Visual c + + 설치 구성 요소에 포함 되었지만 이러한 MFC는 기본적으로 설치 되지에 대 한 지원을 모두 유니코드 및 MBCS MFC Dll입니다. Visual C++ 및 MFC는 Visual Studio 설치 프로그램에서 선택적 설치 구성입니다. MFC가 설치되었는지 확인하려면 설치 프로그램에서 **사용자 지정** 을 선택하고 **프로그래밍 언어**에서 **Visual C++** 및 **C++용 Microsoft Foundation Classes** 가 선택되어 있는지 확인합니다. Visual Studio를 이미 설치한 경우 MFC 프로젝트를 만들려고 하면 Visual C++ 및/또는 MFC를 설치하라는 메시지가 표시됩니다.

**Visual Studio 2017**: 유니코드 및 MBCS MFC Dll와 함께 설치 되는 **c + + 데스크톱 개발** 선택할 때 작업 **MFC 및 ATL 지원** 에서  **선택적 구성 요소** 창. 설치에는 이러한 구성 요소에서 설치 관리자를 시작할 수 있습니다는 **새 프로젝트** 를 사용 하 여 대화 상자는 **Open Visual Studio 설치 관리자** 링크 합니다.

## <a name="see-also"></a>참고 항목

[MFC 라이브러리 버전](../mfc/mfc-library-versions.md)

