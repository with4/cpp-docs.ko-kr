---
title: "BSCMAKE 명령줄 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "BSCMAKE, 명령줄"
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# BSCMAKE 명령줄
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

BSCMAKE를 실행하려면 다음과 같은 명령줄 구문을 사용합니다.  
  
```  
BSCMAKE [options] sbrfiles  
```  
  
 옵션은 명령줄의 `options` 필드에만 나타낼 수 있습니다.  
  
 *sbrfiles* 필드는 컴파일러 또는 어셈블러에서 만든 하나 이상의 .sbr 파일을 지정합니다.  공백 또는 탭을 사용하여 .sbr 파일의 이름을 구분하십시오.  확장명은 기본값이 없으며 사용자가 지정해야 합니다.  파일 이름과 함께 경로를 지정할 수 있고 운영 체제 와일드카드\(\*, ?\)를 사용할 수 있습니다.  
  
 증분 빌드를 수행하는 동안 원래 빌드에 포함되지 않은 새 .sbr 파일을 지정할 수 있습니다.  모든 구성 정보를 찾아보기 정보 파일에 포함시키려면 .bsc 파일을 만들기 위해 처음에 사용한 모든 .sbr 파일\(잘린 파일 포함\)을 지정해야 합니다.  .sbr 파일을 생략하면 찾아보기 정보 파일에 대한 이 파일의 구성 정보가 제거됩니다.  
  
 전체 빌드의 경우 잘린 .sbr 파일을 지정하지 않습니다.  전체 빌드는 지정된 모든 .sbr 파일의 구성 정보를 필요로 합니다.  전체 빌드를 수행하기 전에 프로젝트를 다시 컴파일하여 비어 있는 각 파일에 대해 새 .sbr 파일을 만듭니다.  
  
 다음 명령은 BSCMAKE를 실행하여 3개의 .sbr 파일에서 MAIN.bsc라는 파일을 빌드합니다.  
  
```  
BSCMAKE main.sbr file1.sbr file2.sbr  
```  
  
 관련 내용은 [BSCMAKE 명령 파일](../../build/reference/bscmake-command-file-response-file.md) 및 [BSCMAKE 옵션](../../build/reference/bscmake-options.md)을 참조하십시오.  
  
## 참고 항목  
 [BSCMAKE 참조](../../build/reference/bscmake-reference.md)