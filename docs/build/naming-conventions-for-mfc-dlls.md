---
title: "MFC DLL의 명명 규칙 | Microsoft Docs"
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
  - "DLL[C++], 라이브러리 이름"
  - "DLL[C++], 명명 규칙"
  - "라이브러리[C++], MFC DLL 이름"
  - "MFC DLL[C++], 명명 규칙"
  - "MFC 라이브러리[C++], 명명 규칙"
  - "명명 규칙[C++], MFC DLL"
  - "공유 DLL 버전[C++]"
ms.assetid: 0db9c3f3-87d3-40e8-8964-250f9d2a2209
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# MFC DLL의 명명 규칙
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC에 포함된 DLL 및 라이브러리는 구조적 명명 규칙을 따릅니다.  이 명명 규칙을 따르면 각 용도에 따라 사용해야 하는 DLL 또는 라이브러리에 대해 보다 쉽게 알 수 있습니다.  
  
 이러한 DLL을 사용하는 응용 프로그램 또는 확장 DLL을 빌드하는 데 필요한 가져오기 라이브러리는 DLL과 같은 기본 이름을 갖지만 파일 확장명이 .lib입니다.  
  
### 공유 DLL 명명 규칙  
  
|DLL|설명|  
|---------|--------|  
|MFCx0.DLL|MFC DLL, ANSI 릴리스 버전|  
|MFCx0U.DLL|MFC DLL, 유니코드 릴리스 버전|  
|MFCx0D.DLL|MFC DLL, ANSI 디버그 버전|  
|MFCx0UD.DLL|MFC DLL, 유니코드 디버그 버전|  
  
 MFC의 공유 DLL 버전에 동적으로 링크하는 경우에는 해당 공유 DLL 버전이 응용 프로그램에서 나온 것이든 확장 DLL에서 나온 것이든 상관 없이 MFCx0.DLL을 제품과 함께 포함시켜야 합니다.  응용 프로그램에서 유니코드를 지원해야 하는 경우에는 그 대신 MFCx0U.DLL을 포함시킵니다.  
  
 DLL을 MFC에 정적으로 링크시키는 경우에는 정적 MFC 라이브러리 중 하나를 사용하여 링크시켜야 합니다.  이들 버전은 \[N&#124;U\]AFXCW\[D\].LIB와 같은 규칙에 따라 명명됩니다.  자세한 내용은 [라이브러리 명명 규칙](../mfc/library-naming-conventions.md)\(MFC\)의 "동적 연결 라이브러리 명명 규칙" 표를 참조하십시오.  
  
 응용 프로그램과 함께 배포할 수 있는 Visual C\+\+ DLL 목록은 Visual Studio 설치 폴더에 있는 Redist.txt를 참조하십시오.  
  
## 추가 정보  
  
-   [라이브러리 명명 규칙](../mfc/library-naming-conventions.md)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)