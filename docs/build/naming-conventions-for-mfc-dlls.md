---
title: "MFC Dll에 대 한 명명 규칙 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC libraries [C++], naming conventions
- naming conventions [C++], MFC DLLs
- MFC DLLs [C++], naming conventions
- libraries [C++], MFC DLL names
- shared DLL versions [C++]
- DLLs [C++], naming conventions
- DLLs [C++], library names
ms.assetid: 0db9c3f3-87d3-40e8-8964-250f9d2a2209
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7b78d01405ca74acfa74f898b88d1c9b79625e99
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="naming-conventions-for-mfc-dlls"></a>MFC DLL의 명명 규칙
Dll 및 MFC에 포함 된 라이브러리가 구조적된 명명 규칙을 따릅니다. 이렇게 하면 보다 쉽게는 DLL 또는 라이브러리를 사용 해야 각 용도 대 한 알 수 있습니다.  
  
 가져오기 라이브러리 응용 프로그램 또는 이러한 Dll을 사용 하는 MFC 확장 Dll을 빌드하는 데 필요한 DLL과 같은 기본 이름을 갖지만.lib 파일 이름 확장명이 있습니다.  
  
### <a name="shared-dll-naming-convention"></a>공유 DLL 명명 규칙  
  
|DLL|설명|  
|---------|-----------------|  
|MFCx0.DLL|MFC DLL, ANSI 릴리스 버전|  
|MFCx0U.DLL|MFC DLL, 유니코드 릴리스 버전|  
|MFCx0D.DLL|MFC DLL, ANSI 디버그 버전|  
|MFCx0UD.DLL|MFC DLL, 유니코드 디버그 버전|  
  
 동적으로 연결할 공유 DLL 버전의 MFC 응용 프로그램에서 또는 MFC 확장 DLL에서에서 여부, MFCx0.DLL 제품과 함께 있어야 합니다. 응용 프로그램에서 유니코드 지원이 필요 하면 대신 MFCx0U.DLL를 포함 합니다.  
  
 MFC에 DLL을 한 정적으로 연결 하는 경우에 정적 MFC 라이브러리 중 하나를 사용해를 연결 해야 합니다. 규칙에 따라 이러한 버전 이름은 [N &#124; U] AFXCW [D]입니다. LIB 합니다. 자세한 내용은 "정적 링크 라이브러리 명명 규칙" 표를 참조 [라이브러리 명명 규칙](../mfc/library-naming-conventions.md) (MFC).  
  
 목록이 응용 프로그램과 함께 배포할 수 있는 Visual c + + Dll에 대 한 Visual Studio 설치에서 Redist.txt를 참조 하세요.  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [라이브러리에 대 한 명명 규칙](../mfc/library-naming-conventions.md)  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++의 DLL](../build/dlls-in-visual-cpp.md)