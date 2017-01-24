---
title: "컴파일러 COM 지원 | Microsoft Docs"
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
  - "cl.exe 컴파일러, COM 지원"
  - "COM, 컴파일러 지원"
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 컴파일러 COM 지원
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 Visual C\+\+ 컴파일러는 직접 COM\(구성 요소 개체 모델\) 형식 라이브러리를 읽고 해당 콘텐츠를 컴파일에 포함될 수 있는 C\+\+ 소스 코드로 변환할 수 있습니다.  언어 확장은 클라이언트 쪽에서 COM 프로그래밍을 용이하게 하는 데 사용할 수 있습니다.  
  
 [\#import 전처리기 지시문](../preprocessor/hash-import-directive-cpp.md)을 사용함으로써 컴파일러는 형식 라이브러리를 읽고 COM 인터페이스를 클래스로 설명하는 C\+\+ 헤더 파일로 변환할 수 있습니다.  `#import` 특성 집합은 결과 형식 라이브러리 헤더 파일에 대한 콘텐츠를 사용자가 제어하는 데 사용할 수 있습니다.  
  
 [\_\_declspec](../cpp/declspec.md) 확장 특성인 [uuid](../cpp/uuid-cpp.md)를 사용하여 GUID\(Globally Unique Identifier\)를 COM 개체에 할당할 수 있습니다.  [\_\_uuidof](../cpp/uuidof-operator.md) 키워드는 COM 개체와 연결된 GUID를 추출하는 데 사용할 수 있습니다.  다른 `__declspec` 특성인 [property](../cpp/property-cpp.md)는 COM 개체의 데이터 멤버를 위해 **get** 및 **set** 메서드를 지정하는 데 사용할 수 있습니다.  
  
 COM 집합은 전역 함수를 지원하며 **VARIANT** 및 `BSTR` 형식을 지원하고 스마트 포인터를 구현하고 `_com_raise_error`에 의해 throw되는 오류 개체를 캡슐화하도록 클래스가 제공됩니다.  
  
-   [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)  
  
-   [\_bstr\_t](../cpp/bstr-t-class.md)  
  
-   [\_com\_error](../cpp/com-error-class.md)  
  
-   [\_com\_ptr\_t](../cpp/com-ptr-t-class.md)  
  
-   [\_variant\_t](../cpp/variant-t-class.md)  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [컴파일러 COM 지원 클래스](../cpp/compiler-com-support-classes.md)   
 [컴파일러 COM 전역 함수](../cpp/compiler-com-global-functions.md)