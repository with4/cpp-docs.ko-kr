---
title: "심각한 오류 C1092 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1092"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1092"
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 심각한 오류 C1092
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

편집하며 계속하기는 데이터 형식에 대한 변경 내용은 지원하지 않습니다. 빌드해야 합니다.  
  
 마지막 빌드를 수행한 이후에 데이터 형식을 변경하거나 추가했습니다.  
  
-   편집하며 계속하기는 클래스, 구조체, 열거형 정의를 포함한 기존 데이터 형식에 대한 변경 내용을 지원하지 않습니다.  디버깅을 중지하고 응용 프로그램을 빌드해야 합니다.  
  
-   vc*x*0.pdb\(여기에서 *x*는 사용 중인 주 버전의 Visual C\+\+임\)와 같은 프로그램 데이터베이스 파일이 읽기 전용인 경우 편집하며 계속하기는 새로운 데이터 형식의 추가를 지원하지 않습니다.  데이터 형식을 추가하려면 컴파일러가 .pdb 파일을 쓰기 모드에서 열어야 합니다.  
  
### 현재 디버그 세션을 끝내지 않고 이 오류를 제거하려면  
  
1.  데이터 형식을 오류가 발생하기 전의 상태로 변경합니다.  
  
2.  **디버그** 메뉴에서 **코드 변경 내용 적용**을 선택합니다.  
  
### 소스 코드를 변경하지 않고 이 오류를 제거하려면  
  
1.  **디버그** 메뉴에서 **디버깅 중지**를 선택합니다.  
  
2.  **빌드** 메뉴에서 **빌드**를 선택합니다.  
  
 자세한 내용은 [지원되는 코드 변경](../Topic/Supported%20Code%20Changes%20\(C++\).md)을 참조하십시오.