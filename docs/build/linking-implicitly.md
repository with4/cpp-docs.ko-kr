---
title: "암시적 링크 | Microsoft Docs"
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
  - "암시적 링크[C++]"
  - "로드 시 동적 링크[C++]"
  - "정적 로드 링크[C++]"
ms.assetid: 3ea4c316-4e70-4111-9944-c1b4ad00c605
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 암시적 링크
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DLL에 암시적으로 링크하려면 실행 파일에서 DLL 공급자로부터 다음과 같은 항목을 가져와야 합니다.  
  
-   내보내기 함수 및\/또는 C\+\+ 클래스의 선언이 들어 있는 헤더 파일\(.h 파일\).  클래스, 함수 및 데이터에는 모두 `__declspec(dllimport)`가 있어야 합니다. 자세한 내용은 [dllexport, dllimport](../cpp/dllexport-dllimport.md)를 참조하십시오.  
  
-   링크할 가져오기 라이브러리\([.LIB 파일](../build/reference/dot-lib-files-as-linker-input.md)\). 링커는 DLL이 빌드될 때 가져오기 라이브러리를 만듭니다.  
  
-   실제 DLL\(.dll 파일\)  
  
 DLL을 사용하는 실행 파일에는 내보내기 함수를 호출하는 각 소스 파일마다 내보내기 함수 또는 C\+\+ 클래스가 들어 있는 헤더 파일이 포함되어야 합니다.  코딩 관점에서 볼 때 내보내기 함수를 호출하는 것은 다른 함수 호출과 비슷합니다.  
  
 호출 실행 파일을 빌드하려면 가져오기 라이브러리와 링크해야 합니다.  외부 메이크파일을 사용하는 경우에는 링크할 다른 개체 파일\(.obj\) 또는 라이브러리가 나열된 가져오기 라이브러리의 파일 이름을 지정합니다.  
  
 운영 체제에서 호출 실행 파일을 로드할 때 DLL 파일을 찾을 수 있어야 합니다.  
  
## 수행할 작업  
  
-   [명시적 링크](../build/linking-explicitly.md)  
  
-   [사용할 링크 방법 결정](../build/determining-which-linking-method-to-use.md)  
  
## 추가 정보  
  
-   [가져오기 라이브러리 및 내보내기 파일을 사용한 작업](../build/reference/working-with-import-libraries-and-export-files.md)  
  
-   [Windows에서 DLL을 찾는 데 사용되는 검색 경로](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
## 참고 항목  
 [DLL에 실행 파일 링크](../build/linking-an-executable-to-a-dll.md)