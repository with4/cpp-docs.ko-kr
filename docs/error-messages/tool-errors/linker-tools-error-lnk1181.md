---
title: "링커 도구 오류 LNK1181 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1181"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1181"
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1181
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'filename' 입력 파일을 열 수 없습니다.  
  
 파일 이름이 없거나 경로를 찾을 수 없어서 링커가 `filename`을 찾지 못했습니다.  
  
 LNK1181 오류가 발생하는 일반적인 원인은 다음과 같습니다.  
  
-   링커 줄에서 `filename`이 추가 종속성으로 참조되었지만 이 파일이 없습니다.  
  
-   `filename`이 들어 있는 디렉터리를 지정하는 **\/LIBPATH** 문이 없습니다.  
  
 위 문제를 해결하려면 링커 줄에 참조된 모든 파일이 컴퓨터에 있는지 확인합니다.  또한 링커 종속성 파일이 들어 있는 디렉터리마다 **\/LIBPATH** 명령이 있는지 확인합니다.  
  
 LNK1181 오류는 공백이 포함된 긴 파일 이름을 따옴표로 묶지 않은 경우에도 발생할 수 있습니다.  이 경우 링커에서는 첫 번째 공백까지만 파일 이름으로 인식하고 파일 확장명이 .obj라고 가정합니다.  이 문제를 해결하려면 긴 파일 이름\(경로 및 파일 이름\)을 따옴표로 묶습니다.  
  
 자세한 내용은 [링커 입력 파일로 사용하는 .lib 파일](../../build/reference/dot-lib-files-as-linker-input.md)을 참조하십시오.  
  
## 참고 항목  
 [\/LIBPATH\(추가 Libpath\)](../../build/reference/libpath-additional-libpath.md)