---
title: "대상 | Microsoft Docs"
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
  - "대상, NMAKE에서 지정"
ms.assetid: 826ee849-4278-4c6e-97c3-79a2b5fe6463
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 대상
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

종속 줄에서 유효한 파일 이름, 디렉터리 이름 또는 [의사 대상](../build/pseudotargets.md)을 사용하여 대상을 하나 이상 지정합니다.  대상이 여러 개인 경우에는 공백이나 탭을 사용하여 구분합니다.  대상은 대\/소문자를 구분하지 않습니다.  파일 이름에 경로를 사용할 수 있습니다.  대상은 256자를 초과할 수 없습니다.  콜론 앞에 오는 대상이 단일 문자인 경우 공백을 사용하여 구분합니다. 그렇지 않으면 NMAKE가 문자와 콜론을 합하여 드라이브 지정자로 해석합니다.  
  
## 추가 정보  
 [의사 대상](../build/pseudotargets.md)  
  
 [대상이 여러 개인 경우](../build/multiple-targets.md)  
  
 [누적되는 종속 줄](../build/cumulative-dependencies.md)  
  
 [여러 개의 설명 블록에 포함된 대상](../build/targets-in-multiple-description-blocks.md)  
  
 [종속 줄의 부수적 효과](../build/dependency-side-effects.md)  
  
## 참고 항목  
 [설명 블록](../build/description-blocks.md)