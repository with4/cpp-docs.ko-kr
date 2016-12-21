---
title: "컴파일러 경고 (수준 1) C4651 | Microsoft Docs"
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
  - "C4651"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4651"
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4651
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

미리 컴파일된 헤더에 대해 'definition'을\(를\) 지정했으나 현재 컴파일에 대해서는 지정하지 않았습니다.  
  
 미리 컴파일된 헤더를 생성할 때에는 정의를 지정했지만 현재 컴파일에서는 지정하지 않았습니다.  
  
 미리 컴파일된 헤더에서는 정의가 효력을 발휘하지만 나머지 코드에서는 유효하지 않습니다.  
  
 미리 컴파일된 헤더를 \/DSYMBOL을 사용하여 빌드한 경우 \/Yu 컴파일에 \/DSYMBOL을 지정하지 않으면 컴파일러에서 이 경고가 발생합니다.  이 경고를 해결하려면 \/Yu 명령줄에 \/DSYMBOL을 추가하십시오.