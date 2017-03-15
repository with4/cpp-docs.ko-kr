---
title: "컴파일러 한계 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe 컴파일러, 언어 구문에 대한 제한 사항"
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 한계
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ 표준에서는 다양한 언어 구문에 대한 한도를 권장합니다.  다음은 Visual C\+\+ 컴파일러에서 권장된 한도를 구현하지 않은 경우의 목록입니다.  첫 번째 수는 ISO C\+\+ 11 표준\(INCITS\/ISO\/IEC 14882\-2011\[2012\], Annex B\)으로 설정된 한도이고 두 번째 수는 Visual C\+\+로 구현된 한도입니다.  
  
-   복합 문, 반복 제어 구조체 및 선택 제어 구조체의 중첩 단계 수 \[C\+\+ 표준: 256단계\] \(Visual C\+\+ 컴파일러: 중첩되는 문의 조합에 따라 다르지만 일반적으로 100 및 110단계\)  
  
-   단일 매크로 정의의 매개 변수 개수 \[C\+\+ 표준: 256개\] \(Visual C\+\+ 컴파일러: 127개\)  
  
-   단일 매크로 호출의 인수 개수 \[C\+\+ 표준: 256개\] \(Visual C\+\+ 컴파일러 127개\)  
  
-   문자열 리터럴 또는 와이드 문자열 리터럴의 문자 개수\(연결 후\) \[C\+\+ 표준: 65536자\] \(Visual C\+\+ 컴파일러: 싱글바이트 65535자\(`null` 종결자 포함\), 더블바이트 32767자\(`null` 종결자 포함\)\)  
  
-   단일 `struct-declaration-list` 내 클래스, 구조체 또는 공용 구조체의 중첩 단계 수 \[C\+\+ 표준: 256단계\] \(Visual C\+\+ 컴파일러: 16단계\)  
  
-   생성자 정의의 멤버 이니셜라이저 개수 \[C\+\+ 표준: 6144개\] \(Visual C\+\+ 컴파일러: 6144개 이상\)  
  
-   단일 식별자의 범위 한정자 개수 \[C\+\+ 표준: 256개\] \(Visual C\+\+ 컴파일러: 127개\)  
  
-   중첩된 `extern` 지정의 개수\[C\+\+ 표준: 1024개\] \(Visual C\+\+ 컴파일러: 9개\(전역 범위의 암시적 `extern` 지정 제외 시\) 또는 10개\(전역 범위의 암시적 `extern` 지정 포함 시\)\)  
  
-   템플릿 선언의 템플릿 인수 개수 \[C\+\+ 표준: 1024개\] \(Visual C\+\+ 컴파일러: 2046개\)  
  
## 참고 항목  
 [비표준 동작](../cpp/nonstandard-behavior.md)