---
title: "링커 입력 파일로 사용하는 .Ilk 파일 | Microsoft Docs"
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
  - ".ilk 파일"
  - "ILK 파일"
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 입력 파일로 사용하는 .Ilk 파일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

증분 링크하는 경우 LINK에서는 처음으로 증분 링크할 때 만든 .ilk 상태 파일을 업데이트합니다.  이 파일은 .exe 파일이나 .dll 파일과 같은 기본 이름을 사용하며 확장명은 .ilk입니다.  LINK에서는 후속 증분 링크 도중 이 .ilk 파일을 업데이트합니다.  .ilk 파일이 없으면 LINK에서는 전체 링크를 수행하고 새 .ilk 파일을 만듭니다.  .ilk 파일을 사용할 수 없으면 LINK에서는 비증분 링크를 수행합니다.  증분 링크에 대한 자세한 내용은 [\/INCREMENTAL\(증분 링크\)](../../build/reference/incremental-link-incrementally.md) 옵션을 참조하십시오.  
  
## 참고 항목  
 [LINK 입력 파일](../../build/reference/link-input-files.md)   
 [링커 옵션](../../build/reference/linker-options.md)