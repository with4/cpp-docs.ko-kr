---
title: "register 저장소 클래스 지정자 | Microsoft Docs"
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
  - "레지스터 저장소 클래스"
  - "레지스터 변수"
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# register 저장소 클래스 지정자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 Microsoft C\/C\+\+ 컴파일러는 레지스터 변수에 대한 사용자 요청을 고려하지 않습니다.  하지만 이식성을 위해 **register** 키워드와 연결된 다른 모든 의미 체계는 컴파일러에서 적용됩니다.  예를 들어 단항 address\-of 연산자\(**&**\)를 register 개체에 적용할 수 없거나 배열에서 **register** 키워드를 사용할 수 없습니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [내부 수준 선언에 대한 저장소 클래스 지정자](../c-language/storage-class-specifiers-for-internal-level-declarations.md)