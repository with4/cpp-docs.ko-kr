---
title: "확장 DLL: 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFXDLL 라이브러리"
  - "DLL[C++], 확장"
  - "확장 DLL[C++], 확장 DLL 정보"
  - "MFC DLL[C++], 확장 DLL"
  - "공유 DLL 버전[C++]"
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 확장 DLL: 개요
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC 확장 DLL은 일반적으로 기존의 MFC 라이브러리 클래스에서 파생된 다시 사용할 수 있는 클래스를 구현하는 DLL입니다.  확장 DLL은 MFC의 공유 버전이라고도 하는 MFC의 동적 연결 라이브러리 버전을 사용하여 빌드됩니다.  MFC의 공유 버전을 사용하여 빌드된 MFC 실행 파일\(응용 프로그램 또는 기본 DLL\)만 확장 DLL을 사용할 수 있습니다.  확장 DLL을 사용하면 MFC에서 새로운 사용자 지정 클래스를 파생시킨 다음 DLL을 호출하는 응용 프로그램에 이 확장된 버전의 MFC를 제공할 수 있습니다.  
  
 확장 DLL은 응용 프로그램과 DLL 간에 MFC 파생 개체를 전달하는 데에도 사용할 수 있습니다.  전달된 개체와 연관된 멤버 함수는 개체가 작성되었던 모듈 안에 있습니다.  MFC의 공유 DLL 버전을 사용하면 이 함수들을 정확하게 내보내므로 응용 프로그램과 이를 로드한 확장 DLL 간에 MFC 또는 MFC 파생 개체 포인터를 자유롭게 전달할 수 있습니다.  
  
 확장 DLL의 기본 요구 사항에 맞는 DLL의 예제를 보려면 MFC 샘플 [DLLHUSK](http://msdn.microsoft.com/ko-kr/dfcaa6ff-b8e2-4efd-8100-ee3650071f90)를 참조하십시오.  특히 Testdll1.cpp 및 Testdll2.cpp 파일을 참조하십시오.  
  
 AFXDLL이라는 용어는 Visual C\+\+ 설명서에서 더 이상 사용되지 않습니다.  확장 DLL의 특징은 이전의 AFXDLL 특징과 같습니다.  
  
## 수행할 작업  
  
-   [확장 DLL 초기화](../build/initializing-extension-dlls.md)  
  
## 추가 정보  
  
-   [확장 DLL](../build/extension-dlls.md)  
  
-   [기본 DLL에서 데이터베이스, OLE 및 소켓 확장 DLL 사용](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [비 MFC DLL: 개요](../build/non-mfc-dlls-overview.md)  
  
-   [정적으로 MFC에 링크된 기본 DLL](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [동적으로 MFC에 링크하는 기본 DLL](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC DLL 마법사](../mfc/reference/mfc-dll-wizard.md)  
  
## 참고 항목  
 [DLL 종류](../build/kinds-of-dlls.md)