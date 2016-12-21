---
title: "VCPROFILE_PATH | Microsoft Docs"
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
  - "VCPROFILE_PATH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VCPROFILE_PATH 환경 변수"
ms.assetid: 25217aa4-7e86-4eba-854d-10b3c457e4df
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# VCPROFILE_PATH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

.pgc 파일을 만들 디렉터리를 지정합니다.  
  
## 구문  
  
```  
VCPROFILE_PATH=path  
```  
  
#### 매개 변수  
 `path`  
 .pgc 파일을 추가할 디렉터리 경로입니다.  
  
## 설명  
 기본적으로 .pgc 파일은 프로파일링하는 이진 파일과 동일한 디렉터리에 만들어집니다.  그러나 이진 파일을 빌드했던 다른 컴퓨터에서 프로파일링 시나리오를 실행하는 경우와 같이 이진 파일의 절대 경로가 없으면 기존의 경로로 `VCPROFILE_PATH`를 설정할 수 있습니다.  
  
## 예제  
  
```  
set VCPROFILE_PATH=c:\  
```  
  
## 참고 항목  
 [프로필 기반 최적화 환경 변수](../../build/reference/environment-variables-for-profile-guided-optimizations.md)