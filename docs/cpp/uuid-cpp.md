---
title: "uuid (C++) | Microsoft Docs"
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
  - "uuid"
  - "uuid_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec 키워드[C++], uuid"
  - "uuid __declspec 키워드"
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# uuid (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 컴파일러는 `uuid` 특성을 사용하여 선언되거나 정의된\(전체 COM 개체 정의만 해당\) 클래스 또는 구조체에 GUID를 연결합니다.  
  
## 구문  
  
```  
  
__declspec( uuid("  
ComObjectGUID  
") ) declarator  
```  
  
## 설명  
 `uuid` 특성은 문자열을 인수로 사용합니다.  이 문자열은 **{}** 구분 기호를 사용하거나 사용하지 않고 일반 레지스트리 형식으로 GUID 이름을 지정합니다.  예를 들면 다음과 같습니다.  
  
```  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;  
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;  
```  
  
 재선언에서 이 특성을 적용할 수 있습니다.  그러면 시스템 헤더가 **IUnknown** 등의 인터페이스 정의와 일부 다른 헤더의 재선언을 제공하여 GUID를 제공할 수 있습니다.  
  
 [\_\_uuidof](../cpp/uuidof-operator.md) 키워드를 적용하여 사용자 정의 형식에 연결된 상수 GUID를 검색할 수 있습니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)