---
title: "링커 도구 경고 LNK4014 | Microsoft Docs"
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
  - "LNK4014"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4014"
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 경고 LNK4014
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

objectname 멤버 개체를 찾을 수 없습니다.  
  
 LIB가 라이브러리에서 `objectname`을 찾지 못했습니다.  
  
 **\/REMOVE** 및 **\/EXTRACT** 옵션에는 삭제하거나 파일에 복사할 멤버 개체의 전체 이름이 필요합니다.  전체 이름에는 원본 개체 파일의 경로가 포함됩니다.  라이브러리에 있는 멤버 개체의 전체 이름을 알아보려면 DUMPBIN [\/ARCHIVEMEMBERS](../../build/reference/archivemembers.md) 또는 LIB [\/LIST](../../build/reference/managing-a-library.md)를 사용하십시오.