---
title: "@(컴파일러 지시 파일 지정) | Microsoft Docs"
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
  - "@"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "@ 컴파일러 옵션"
  - "cl.exe 컴파일러, 컴파일러 지시 파일 지정"
  - "지시 파일, C/C++ 컴파일러"
ms.assetid: 400fffee-909d-4f60-bf76-45833e822685
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# @(컴파일러 지시 파일 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러 지시 파일을 지정합니다.  
  
## 구문  
  
```  
@response_file  
```  
  
## 인수  
 `response_file`  
 컴파일러 명령을 포함하는 텍스트 파일  
  
## 설명  
 지시 파일은 명령줄에 지정할 수 있는 모든 명령을 포함할 수 있습니다.  명령줄 인수가 127 문자를 초과 하는 경우에 유용할 수 있습니다.  
  
 지시 파일 내에서 **@** 옵션을 지정할 수 없습니다.  즉, 지시 파일은 다른 지시 파일을 포함할 수 없습니다.  
  
 필요한 여러 지시 파일 옵션\(예: `@respfile.1 @respfile.2`\)을 명령줄에서 지정할 수 있습니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
-   지시 파일은 개발 환경에서는 지정할 수 없고 명령줄에서만 지정할 수 있습니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   이 컴파일러 옵션은 프로그래밍 방식으로 변경할 수 없습니다.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)