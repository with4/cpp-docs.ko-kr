---
title: "링커 도구 경고 LNK4204 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4204"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4204"
ms.assetid: 14adda20-0cbe-407b-90f6-9f81c93530e2
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 링커 도구 경고 LNK4204
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'filename'에 참조 모듈에 대한 디버깅 정보가 없습니다. 디버그 정보가 없는 것처럼 개체를 링크합니다.  
  
 .pdb 파일에 잘못된 시그니처가 있습니다.  링커가 디버그 정보 없이 개체를 계속 링크합니다.  [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) 옵션을 사용하여 개체 파일을 다시 컴파일할 수도 있습니다.  
  
 LNK4204는 라이브러리의 개체 중 일부가 더 이상 존재하지 않는 파일을 참조할 때 발생합니다.  솔루션을 다시 빌드할 때 이러한 문제가 발생할 수 있습니다. 예를 들어 컴파일러 오류로 인해 개체 파일이 삭제되어 다시 빌드되지 않을 수 있습니다.  이 경우 **\/Z7** 또는 **\/Fd**로 컴파일하여 기본 .pdb 파일 이름이 아닌 라이브러리별 단일 파일을 참조하도록 개체를 업데이트합니다.  자세한 내용은 [\/Fd\(프로그램 데이터베이스 파일 이름\)](../../build/reference/fd-program-database-file-name.md)을 참조하십시오.  소스 제어 시스템에서 라이브러리가 업데이트될 때마다 .pdb를 함께 저장해야 합니다.