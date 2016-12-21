---
title: "/Zc:auto(변수 형식 추론) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Zc:auto"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc 컴파일러 옵션(C++)"
  - "Deduce 변수 형식(C++)"
  - "Zc 컴파일러 옵션(C++)"
  - "-Zc 컴파일러 옵션(C++)"
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:auto(변수 형식 추론)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/Zc:auto\[\-\]** 컴파일러 옵션은 컴파일러에 [auto keyword](../../cpp/auto-keyword.md)를 사용하여 변수를 선언하는 방법을 지시합니다.  기본 옵션인 **\/Zc:auto**를 지정하면 컴파일러는 초기화 식에서 선언된 변수 형식을 추론합니다.   **\/Zc:auto\-**를 지정하면 컴파일러가 자동 저장소 클래스에 선언된 변수를 할당합니다.  
  
## 구문  
  
```  
/Zc:auto[-]  
```  
  
## 설명  
 C\+\+ 표준에는 `auto` 키워드의 원래 의미와 수정된 의미가 정의되어 있습니다.  [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)] 전까지 이 키워드는 자동 저장소 클래스에 있는 변수, 즉 지역 변수를 선언합니다.  [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)]부터 이 키워드는 선언의 초기화에서 변수 유형을 추론합니다. **\/Zc:auto\[\-\]** 컴파일러 옵션을 사용하여 컴파일러에 `auto` 키워드의 원래 의미 또는 수정된 의미를 사용하도록 지시합니다.  
  
 `auto` 키워드 사용이 현재 컴파일러 옵션과 모순되는 경우 컴파일러는 적절한 진단 메시지를 표시합니다.  자세한 내용은 [auto 키워드](../../cpp/auto-keyword.md)을 참조하십시오.  Visual C\+\+의 규칙과 관련된 문제에 대한 자세한 내용은 [비표준 동작](../../cpp/nonstandard-behavior.md)를 참조하십시오.  
  
### Visual Studio에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **구성 속성** 노드를 클릭합니다.  
  
3.  **C\/C\+\+** 노드를 클릭합니다.  
  
4.  **명령줄** 노드를 클릭합니다.  
  
5.  **추가 옵션:** 창에 **\/Zc:auto** 또는 **\/Zc:auto\-**를 추가합니다.  
  
## 참고 항목  
 [\/Zc\(규칙\)](../../build/reference/zc-conformance.md)   
 [auto 키워드](../../cpp/auto-keyword.md)