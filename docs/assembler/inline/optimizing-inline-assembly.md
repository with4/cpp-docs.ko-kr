---
title: "인라인 어셈블리 최적화 | Microsoft Docs"
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
  - "__asm 키워드[C++], 최적화"
  - "인라인 어셈블리, 최적화"
  - "최적화, 인라인 어셈블리"
  - "성능 최적화, 인라인 어셈블리"
  - "저장소, 인라인 어셈블리에서 최적화"
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 인라인 어셈블리 최적화
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 함수에 `__asm` 블록이 있으면 여러 가지 방식으로 최적화에 영향을 받습니다.  먼저, 컴파일러는 `__asm` 블록 자체를 최적화하려고 하지 않습니다.  어셈블리 언어로 작성한 내용대로 결과가 발생합니다.  다음으로, `__asm` 블록이 있음으로 인해 레지스터 변수 저장에 영향을 줍니다.  컴파일러는 레지스터의 콘텐츠가 `__asm` 블록에 의해 변경될 경우 `__asm` 블록 전체에서 변수를 등록하지 않습니다.  마지막으로, 함수에 어셈블리 언어를 포함하면 일부 다른 함수 차원의 최적화에 영향을 줍니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [인라인 어셈블러](../../assembler/inline/inline-assembler.md)