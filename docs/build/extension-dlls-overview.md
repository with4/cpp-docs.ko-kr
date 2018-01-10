---
title: "확장 Dll: 개요 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- AFXDLL library
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 407ed0c63dce8e350c24ac5f260876fb6ab47576
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-extension-dlls-overview"></a>MFC 확장명 Dll: 개요
MFC 확장 DLL은 일반적으로 기존 Microsoft Foundation Class 라이브러리 클래스에서 파생 된 다시 사용할 수 있는 클래스를 구현 하는 DLL입니다. MFC 확장명 Dll은 MFC (MFC 공유 버전 라고도 함)의 동적 연결 라이브러리 버전을 사용 하 여 작성 됩니다. 만 MFC 실행 파일 (응용 프로그램 또는 일반 MFC Dll)의 MFC 공유 버전으로 작성 하는 MFC 확장 DLL을 사용할 수 있습니다. MFC 확장 DLL MFC에서 새로운 사용자 지정 클래스를 파생 시킨 수 있으며 다음이 확장 된 버전의 MFC DLL을 호출 하는 응용 프로그램을 제공할 수 있습니다.  
  
 응용 프로그램과 DLL 사이의 MFC 파생 개체를 전달 하기 위한 확장 Dll은 사용할 수도 있습니다. 전달된 된 개체와 연결 된 멤버 함수는 개체가 생성 된 모듈에 있습니다. 이러한 함수는 내보내지므로 제대로 mfc 공유 DLL 버전을 사용 하는 경우, MFC 자유롭게 전달할 수 있습니다 또는 MFC에서 파생 된 개체 포인터 응용 프로그램과 MFC 확장 Dll 로드 합니다.  
  
 MFC 확장 DLL의 기본 요구 사항을 충족 하는 DLL의 예를 들어 MFC 샘플을 참조 하십시오. [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk)합니다. 특히 Testdll1.cpp 및 Testdll2.cpp 파일을 살펴봅니다.  
  
 AFXDLL 용어는 Visual c + + 설명서에 더 이상 사용 되는 참고 합니다. MFC 확장 DLL은 이전 AFXDLL와 동일한 특성입니다.  
  
## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
-   [MFC 확장 DLL 초기화](../build/run-time-library-behavior.md#initializing-extension-dlls)  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [MFC 확장명 DLL](../build/extension-dlls.md)  
  
-   [기본 MFC DLL에서 데이터베이스, OLE 및 소켓 MFC 확장명 DLL 사용](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [비 MFC DLL: 개요](../build/non-mfc-dlls-overview.md)  
  
-   [기본 MFC Dll에 정적으로 MFC에 링크](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [동적으로 MFC에 링크 하는 기본 MFC Dll](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC DLL 만들기](../mfc/reference/mfc-dll-wizard.md)  
  
## <a name="see-also"></a>참고 항목  
 [DLL의 종류](../build/kinds-of-dlls.md)