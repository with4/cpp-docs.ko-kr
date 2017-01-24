---
title: "링커 명령줄 구문 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LINK 도구[C++], 명령줄 구문"
  - "링커[C++], 구문"
  - "링커 명령줄 구문[C++]"
ms.assetid: e2a31e17-77bd-4e74-9305-75b105b26539
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 명령줄 구문
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LINK.EXE를 실행하려면 다음 명령 구문을 사용합니다.  
  
```  
LINK arguments  
```  
  
 `arguments`에는 옵션과 파일 이름이 포함되며 지정 순서는 상관 없습니다.  옵션이 먼저 처리되고 그 다음에 파일이 처리됩니다.  각 인수 사이에는 공백이나 탭을 사용하여 구분합니다.  
  
> [!NOTE]
>  이 도구는 [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] 명령 프롬프트에서만 시작할 수 있습니다.  시스템 명령 프롬프트 또는 파일 탐색기에서는 시작할 수 없습니다.  
  
 명령줄의 옵션은 옵션 지정자인 대시\(\-\) 또는 슬래시\(\/\)와 옵션 이름으로 구성됩니다.  옵션 이름은 약식으로 표기할 수 없습니다.  일부 옵션의 경우에는 콜론\(:\) 뒤에 인수를 지정합니다.  옵션을 지정할 때 공백이나 탭은 \/COMMENT 옵션에서 따옴표로 묶은 문자열에만 사용할 수 있습니다.  숫자 인수는 십진수나 C 언어 표기법으로 지정합니다.  옵션 이름과 해당 키워드 또는 파일 이름 인수는 대\/소문자를 구분하지 않지만 인수로 지정되는 식별자는 대\/소문자를 구분합니다.  
  
 파일을 링커에 전달하려면 명령줄에서 LINK 명령 뒤에 파일 이름을 지정합니다.  파일 이름이 포함된 절대 경로나 상대 경로를 지정할 수 있으며 파일 이름에 와일드카드를 사용할 수도 있습니다.  마침표\(.\)와 파일 확장명을 생략하면 .obj로 가정하여 해당 파일을 찾게 됩니다.  LINK에서는 파일 확장명을 사용하지 않으며, 파일 확장명이 없으면 해당 파일로 가정합니다. 파일 내용을 검사하여 파일 형식을 결정하고 그 결과에 따라 처리합니다.  
  
 link.exe는 오류가 발생하지 않고 작업에 성공하는 경우 0을 반환합니다.  그렇지 않으면 링크를 중지한 오류의 해당 번호가 링커에서 반환됩니다.  예를 들어, 링커에서 LNK1104 생성, 링커가 1104를 반환 합니다. 따라서 링커 오류가 반환 가장 낮은 오류 번호는 1000입니다. 반환 값 128은 운영 체제나.config 파일에 구성 문제가 나타냅니다. 로더는 link.exe 나 c2.dll 로드 하지 않습니다.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)