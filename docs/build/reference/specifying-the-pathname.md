---
title: "경로 이름 지정 | Microsoft Docs"
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
  - "cl.exe 컴파일러, 출력 파일"
  - "이름[C++], 컴파일러 출력 파일"
  - "출력 파일, 경로 이름 지정"
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 경로 이름 지정
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

각 출력 파일 옵션에 *pathname* 인수를 사용하여 출력 파일의 위치와 이름을 지정할 수 있습니다.  이 인수에 드라이브 이름, 디렉터리 및 파일 이름을 포함할 수 있습니다.  옵션과 인수 사이에 공백이 있으면 안 됩니다.  
  
 *pathname* 인수에 확장명 없이 파일 이름만 지정하면 컴파일러가 기본 확장명을 사용하여 출력 파일을 만듭니다.  *pathname* 인수에 파일 이름 없이 디렉터리만 지정하면 컴파일러가 기본 이름을 사용하여 지정된 디렉터리에 파일을 만듭니다.  기본 이름은 소스 파일의 기본 이름을 사용하고 기본 확장명은 출력 파일의 형식을 사용합니다.  *pathname* 전체를 생략하면 컴파일러가 기본 이름을 사용하여 기본 디렉터리에 파일을 만듭니다.  
  
 또한, *pathname* 인수에 파일 이름 대신 장치 이름\(AUX, CON, PRN 또는 NUL\)을 사용할 수도 있습니다.  옵션과 장치 이름 사이에 공백을 넣거나 장치 이름에 콜론을 포함하지 마십시오.  
  
|장치 이름|내용|  
|-----------|--------|  
|AUX|보조 장치|  
|CON|콘솔|  
|PRN|Printer|  
|NUL|Null 장치\(파일을 만들지 않음\)|  
  
## 예제  
 다음 명령줄을 실행하면 맵 파일을 프린터로 보냅니다.  
  
```  
CL /FmPRN HELLO.CPP  
```  
  
## 참고 항목  
 [출력 파일\(\/F\) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)