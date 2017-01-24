---
title: "C 선언 및 정의 | Microsoft Docs"
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
ms.assetid: 575f0c9b-5554-4346-be64-b2129ca9227f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C 선언 및 정의
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

"선언"은 특정 변수, 함수 또는 형식과 해당 특성을 연결합니다.  [선언 개요](../c-language/overview-of-declarations.md)는 `declaration` 비터미널에 대한 ANSI 구문을 제공합니다.  선언은 식별자에 액세스할 수 있는 위치 및 경우도 지정합니다\(식별자의 "링크"\).  링크에 대한 자세한 내용은 [수명, 범위, 표시 유형 및 링크](../c-language/lifetime-scope-visibility-and-linkage.md)를 참조하십시오.  
  
 변수의 "정의"는 선언과 동일한 연결을 설정하지만 변수에 저장소가 할당되게도 만듭니다.  
  
 예를 들어, `main`, `find` 및 `count` 함수와 `var` 및 `val` 변수는 한 소스 파일에서 다음과 같은 순서대로 정의됩니다.  
  
```  
int main() {}  
  
int var = 0;  
double val[MAXVAL];  
char find( fileptr ) {}  
int count( double f ) {}  
```  
  
 `find` 및 `count` 함수에 `var` 및 `val` 변수를 사용할 수 있으며 추가 선언은 필요하지 않습니다.  그러나 이러한 이름은 `main`에 표시되지 않습니다\(액세스할 수 없음\).  
  
## 참고 항목  
 [원본 파일 및 원본 프로그램](../c-language/source-files-and-source-programs.md)