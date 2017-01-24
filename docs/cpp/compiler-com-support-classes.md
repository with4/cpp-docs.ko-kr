---
title: "컴파일러 COM 지원 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_raise_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe 컴파일러, COM 지원"
  - "COM, 컴파일러 지원"
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 컴파일러 COM 지원 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 표준 클래스는 COM 형식 중 일부를 지원하는 데 사용됩니다.  클래스는 comdef.h 및 형식 라이브러리에서 생성된 헤더 파일에 정의됩니다.  
  
|클래스|용도|  
|---------|--------|  
|[\_bstr\_t](../cpp/bstr-t-class.md)|`BSTR` 형식을 래핑하여 유용한 연산자와 메서드를 제공합니다.|  
|[\_com\_error](../cpp/com-error-class.md)|대부분의 오류에서 [\_com\_raise\_error](../cpp/com-raise-error.md)에 의해 throw되는 오류 개체를 정의합니다.|  
|[\_com\_ptr\_t](../cpp/com-ptr-t-class.md)|COM 인터페이스 포인터를 캡슐화하고 `AddRef`, **Release** 및 `QueryInterface`에 대한 필수 호출을 자동화합니다.|  
|[\_variant\_t](../cpp/variant-t-class.md)|**VARIANT** 형식을 래핑하여 유용한 연산자와 메서드를 제공합니다.|  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [컴파일러 COM 지원](../cpp/compiler-com-support.md)   
 [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)   
 [C\+\+ 언어 참조](../cpp/cpp-language-reference.md)