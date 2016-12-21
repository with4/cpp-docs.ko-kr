---
title: "Naked (C) | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "에필로그 코드"
  - "naked 키워드[C]"
  - "naked 키워드[C], 저장소 클래스 특성"
  - "프롤로그 코드"
ms.assetid: 23b1209b-93ba-46ad-a60f-2327c1933eaf
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Naked (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 naked 저장소 클래스 특성은 Microsoft 전용 C 언어 확장입니다.  컴파일러는 naked 저장소 클래스 특성으로 선언된 함수의 코드를 프롤로그 및 에필로그 코드 없이 생성합니다.  naked 함수는 인라인 어셈블러 코드로 사용자 정의 프롤로그\/에필로그 코드 시퀀스를 작성해야 하는 경우 유용합니다.  naked 함수는 가상 장치 드라이버 작성할 때도 유용합니다.  
  
 naked 특성 사용에 대한 자세한 내용은 [Naked 함수](../c-language/naked-functions.md)를 참조하십시오.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [C 확장 저장소 클래스 특성](../c-language/c-extended-storage-class-attributes.md)