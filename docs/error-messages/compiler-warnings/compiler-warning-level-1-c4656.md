---
title: "컴파일러 경고 (수준 1) C4656 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4656"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4656"
ms.assetid: b5aaef74-2320-4345-a6ae-b813881a491c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4656
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' : 데이터 형식이 최근 빌드 후 새로 만들어졌거나 변경되었습니다. 또는 다른 곳에서 다르게 정의되었습니다.  
  
 데이터 형식을 추가하거나 변경하여 최근 빌드 후 소스 코드에 새로운 변경 사항이 생겼습니다.  편집하며 계속하기는 기존 데이터 형식에 대한 변경 내용은 지원하지 않습니다.  
  
 이 경고가 발생한 다음에는 항상 [심각한 오류 C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md)가 발생합니다.  자세한 내용은 [지원되는 코드 변경](../Topic/Supported%20Code%20Changes%20\(C++\).md)을 참조하십시오.  
  
### 현재 디버그 세션을 끝내지 않고 이 경고를 제거하려면  
  
1.  데이터 형식을 오류가 발생하기 전의 상태로 변경합니다.  
  
2.  **디버그** 메뉴에서 **코드 변경 내용 적용**을 선택합니다.  
  
### 소스 코드를 변경하지 않고 이 오류를 제거하려면  
  
1.  **디버그** 메뉴에서 **디버깅 중지**를 선택합니다.  
  
2.  **빌드** 메뉴에서 **빌드**를 선택합니다.