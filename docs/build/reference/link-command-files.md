---
title: "LINK 명령 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "명령 파일[C++]"
  - "명령 파일[C++], LINK"
  - "LINK 도구[C++]"
  - "LINK 도구[C++], 명령줄 구문"
  - "구문, LINK 명령 파일"
  - "텍스트 파일, LINK에 인수 전달"
ms.assetid: 7154511c-32b9-4e5b-a515-3922fa9de48e
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# LINK 명령 파일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LINK에 명령 파일 형식으로 명령줄 인수를 지정할 수 있습니다.  링커에 명령 파일을 지정하려면 다음 구문을 사용합니다.  
  
```  
LINK @commandfile  
```  
  
 `commandfile`은 텍스트 파일의 이름입니다.  @ 기호와 파일 이름 사이에는 공백이나 탭을 사용할 수 없습니다.  기본 확장명이 없으므로 확장명을 포함한 전체 경로를 지정해야 합니다.  와일드카드는 사용할 수 없습니다.  또한 파일 이름이 포함된 절대 경로나 상대 경로를 지정할 수 있습니다.  LINK에서는 환경 변수를 사용하지 않고 파일을 검색합니다.  
  
 명령 파일에서는 명령줄에서와 마찬가지로 공백이나 탭 또는 줄 바꿈 문자를 사용하여 인수를 구분할 수 있습니다.  
  
 명령 파일에서 명령줄 전체 또는 일부를 지정할 수 있습니다.  LINK 명령에는 하나 이상의 명령 파일을 사용할 수 있습니다.  LINK에서는 명령 파일 입력이 명령줄의 해당 위치에 지정된 것처럼 적용합니다.  명령 파일을 중첩할 수는 없습니다.  [\/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md) 옵션을 지정하지 않으면 LINK에서는 명령 파일의 내용을 화면에 표시합니다.  
  
## 예제  
 다음 명령을 사용하여 DLL을 빌드하면 각 명령 파일에 있는 개체 파일과 라이브러리의 이름이 전달되고 세 번째 명령 파일을 사용하여 \/EXPORTS 옵션이 지정됩니다.  
  
```  
link /dll @objlist.txt @liblist.txt @exports.txt  
```  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)