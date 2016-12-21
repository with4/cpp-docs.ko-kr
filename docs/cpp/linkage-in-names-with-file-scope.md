---
title: "파일 범위가 있는 이름의 링크 | Microsoft Docs"
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
  - "선언[C++], 외부"
  - "외부 링크, 범위 링크 규칙"
  - "파일 범위[C++]"
  - "링크[C++], 범위 링크 규칙"
  - "이름[C++], 범위 링크 규칙"
  - "범위[C++], 링크 규칙"
  - "static 한정자, 파일 범위"
  - "정적 이름 및 파일 범위"
  - "정적 변수, 외부 선언"
ms.assetid: 38d3fa5e-1861-466e-a590-84b86f7b184e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 파일 범위가 있는 이름의 링크
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 링크 규칙이 파일 범위가 있는 이름\(`typedef` 및 열거자 이름 제외\)에 적용됩니다.  
  
-   이름이 **static**으로 명시적 선언된 경우, 내부 링크가 있으며 자체 변환 단위 내부의 프로그램 요소가 식별됩니다.  
  
-   열거자 이름 및 `typedef` 이름에는 링크가 없습니다.  
  
-   파일 범위가 있는 다른 모든 이름에는 외부 링크가 있습니다.  
  
 **Microsoft 전용**  
  
-   파일 범위가 있는 함수 이름이 **inline**으로 명시적 선언된 경우 해당 함수 이름이 인스턴스화되거나 주소가 참조되면 외부 링크를 가질 수 있습니다.  따라서 파일 범위가 있는 함수는 내부 또는 외부 링크를 가질 수 있습니다.  
  
 **Microsoft 전용 종료**  
  
 클래스가 내부 링크를 가지는 경우는 다음과 같습니다.  
  
-   예를 들어 멤버 액세스 제어, 멤버 함수, 생성자, 소멸자 등의 C\+\+ 기능을 사용하지 않습니다.  
  
-   외부 링크가 있는 다른 이름 선언에 사용되지 않습니다.  이 제한은 외부 연결을 가진 함수에 클래스 형식의 개체가 전달될 경우 클래스가 외부 연결을 가질 수 있도록 한다는 것을 의미합니다.  
  
## 참고 항목  
 [프로그램 및 링크](../cpp/program-and-linkage-cpp.md)