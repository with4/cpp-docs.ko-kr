---
title: "CL 명령 파일 | Microsoft Docs"
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
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe 컴파일러, 명령 파일"
  - "명령 파일"
  - "명령 파일, CL 컴파일러"
ms.assetid: ec3cea06-2af0-4fe9-a94c-119c9d31b3a9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# CL 명령 파일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

명령 파일이란 [명령줄](../../build/reference/compiler-command-line-syntax.md)에서 입력하거나 [CL 환경 변수](../../build/reference/cl-environment-variables.md)를 사용하여 지정할 옵션과 파일 이름이 들어 있는 텍스트 파일입니다.  CL은 컴파일러 명령 파일을 CL 환경 변수나 명령줄에서 인수로 사용합니다.  명령줄이나 CL 환경 변수와는 달리 명령 파일을 사용하면 여러 줄로 구성된 옵션과 파일 이름을 사용할 수 있습니다.  
  
 명령 파일의 옵션과 파일 이름은 CL 환경 변수나 명령줄에서 명령 파일 이름의 위치에 따라 처리됩니다.  그러나 \/link 옵션이 명령 파일에 나오면 해당 줄의 나머지 부분에 있는 모든 옵션이 링커에 전달됩니다.  명령 파일에서 다음 줄에 나오는 옵션과 명령 파일 호출 다음에 나오는 명령줄의 옵션은 컴파일러 옵션으로 인식됩니다.  옵션의 순서가 해석에 미치는 영향에 대한 자세한 내용은 [CL 옵션 순서](../../build/reference/order-of-cl-options.md)를 참조하십시오.  
  
 명령 파일에는 CL 명령을 포함할 수 없습니다.  각 옵션의 시작과 끝은 같은 줄에 있어야 하며, 백슬래시\(\\\)를 사용하더라도 하나의 옵션을 두 줄에 걸쳐 이어쓸 수 없습니다.  
  
 명령 파일은 파일 이름 앞에 @ 기호를 사용하여 지정합니다. 이 파일 이름에는 절대 및 상대 경로를 사용할 수 있습니다.  
  
 예를 들어, 다음 명령이 RESP라는 파일에 있고  
  
```  
/Og /link LIBC.LIB  
```  
  
 다음 CL 명령을 지정하면  
  
```  
CL /Ob2 @RESP MYAPP.C  
```  
  
 CL에 대한 명령은 다음과 같습니다.  
  
```  
CL /Ob2 /Og MYAPP.C /link LIBC.LIB  
```  
  
 명령줄과 명령 파일에 사용하는 명령은 위에서와 같이 효율적으로 결합하는 것이 좋습니다.  
  
## 참고 항목  
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)