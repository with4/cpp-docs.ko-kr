---
title: "추가 시작 고려 사항 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "main 전에 초기화"
  - "프로그램 시작[C++]"
  - "시작 코드"
ms.assetid: 0e942aa6-8342-447c-b068-8980ed7622bd
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 추가 시작 고려 사항
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+에서 개체 생성 및 소멸 시 실행할 사용자 코드를 포함할 수 있습니다.  따라서, 어떤 초기화가 **main** 시작 전에 발생하며, 어떤 소멸자가 **main** 종료 후에 발생하는가를 이해하는 것이 중요합니다. 개체의 생성과 소멸에 대한 자세한 내용은 [생성자](../cpp/constructors-cpp.md) 및 [소멸자](../cpp/destructors-cpp.md)를 참조하십시오.  
  
 다음과 같은 초기화는 **main**이 시작되기 전에 발생합니다.  
  
-   기본 초기화는 정적 데이터를 0으로 설정합니다.  명시적 이니셜라이저가 없는 모든 정적 데이터는 런타임 이니셜라이저 및 다른 코드를 실행하기 전에 0으로 설정됩니다.  정적 데이터 멤버는 명시적으로 정의되어야 합니다.  
  
-   변환 단위에서 전역 정적 개체를 초기화합니다.  이는 개체의 변환 단위에서 **main**이 시작되기 전 또는 함수나 개체를 처음 사용하기 전에 발생할 수 있습니다.  
  
 **Microsoft 전용**  
  
 Microsoft C\+\+에서 전역 정적 개체는 **main**이 시작되기 전에 초기화됩니다.  
  
 **Microsoft 전용 종료**  
  
 전역 정적 개체는 상호 의존적이지만, 변환 단위가 다른 전역 정적 개체에서는 잘못된 동작이 발생할 수 있습니다.  
  
## 참고 항목  
 [시작 및 종료](../cpp/startup-and-termination-cpp.md)