---
title: "컴파일러 제어 LINK 옵션 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe 컴파일러[C++], 링커 제어"
  - "cl.exe 컴파일러[C++], 링크에 영향을 주는 기능"
  - "LINK 도구[C++], 컴파일러 제어 옵션"
  - "링커[C++], CL 컴파일러 제어"
  - "링크[C++], CL 기능에 의한 영향"
ms.assetid: e4c03896-c99c-4599-8502-e0f4bebe69d0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 제어 LINK 옵션
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CL 컴파일러에서는 \/c 옵션을 지정하지 않으면 자동으로 LINK를 호출합니다.  CL에서는 명령줄 옵션과 인수를 사용하여 링커를 제어할 수 있습니다.  다음은 링크에 영향을 주는 CL 기능입니다.  
  
|CL 사양|LINK에 영향을 주는 CL 동작|  
|-----------|------------------------|  
|c, .cxx, .cpp, .def 이외의 모든 파일 확장명|파일 이름을 LINK에 입력으로 전달합니다.|  
|*filename*.def|\/DEF:*filename*.def를 전달합니다.|  
|\/F`number`|\/STACK:`number`를 전달합니다.|  
|\/Fd*filename*|\/PDB:*filename*을 전달합니다.|  
|\/Fe*filename*|\/OUT:*filename*을 전달합니다.|  
|\/Fm*filename*|\/MAP:*filename*을 전달합니다.|  
|\/Gy|패키지 함수\(COMDAT\)를 만들어 함수 수준 링크를 활성화합니다.|  
|\/LD|\/DLL을 전달합니다.|  
|\/LDd|\/DLL을 전달합니다.|  
|\/link|명령줄의 나머지 부분을 LINK에 전달합니다.|  
|\/MD 또는 \/MT|기본 라이브러리 이름을 .obj 파일에 넣습니다.|  
|\/MDd 또는 \/MTd|기본 라이브러리 이름을 .obj 파일에 넣고  **\_DEBUG** 기호를 정의합니다.|  
|\/nologo|\/NOLOGO를 전달합니다.|  
|\/Zd|\/DEBUG를 전달합니다.|  
|\/Zi, \/Z7|\/DEBUG를 전달합니다.|  
|\/Zl|.obj 파일에서 기본 라이브러리 이름을 생략합니다.|  
  
 자세한 정보는 [컴파일러 옵션](../../build/reference/compiler-options.md)을 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)