---
title: "원시 네이티브 형식 | Microsoft Docs"
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
  - "raw_native_types"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "raw_native_types 특성"
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 원시 네이티브 형식
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 전용**  
  
 상위 수준의 래퍼 함수에서 COM 지원 클래스를 사용하지 않도록 설정하고 대신 하위 수준의 데이터 형식을 사용하도록 합니다.  
  
## 구문  
  
```  
raw_native_types  
```  
  
## 설명  
 기본적으로 상위 오류 처리 메서드는 `BSTR` 및 **VARIANT** 데이터 형식 및 원시 COM 인터페이스 포인터 대신 COM 지원 클래스 [\_bstr\_t](../cpp/bstr-t-class.md) 및 [\_variant\_t](../cpp/variant-t-class.md)를 사용합니다.  이 클래스는 이러한 데이터 형식의 메모리 저장소 할당 및 할당 해제에 대한 정보를 캡슐화합니다.  
  
 **C\+\+ 전용 종료**  
  
## 참고 항목  
 [\#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import 지시문](../preprocessor/hash-import-directive-cpp.md)