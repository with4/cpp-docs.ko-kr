---
title: "Memory Management with CStringT | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStringT"
  - "ATL::CStringT"
  - "ATL.CStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFixedStringT class, description of"
  - "CString objects, 메모리 관리"
  - "CStringT class, 메모리 관리"
  - "IAtlStringMgr class, using"
  - "메모리[C++], 사용법"
  - "문자열[C++], custom memory management"
  - "문자열[C++], 메모리 관리"
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Memory Management with CStringT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

클래스  [CStringT](../atl-mfc-shared/reference/cstringt-class.md) 가변 길이 문자열을 조작 하는 데 사용 하는 템플릿 클래스입니다.  이러한 문자열을 저장할 메모리를 할당 하 고 문자열의 각 인스턴스와 관련 된 관리자 개체를 통해 발표 된 `CStringT`.  ATL 및 MFC의 기본 인스턴스를 제공 `CStringT`, 호출 `CString`, `CStringA`, 및 `CStringW`, 문자열 형식의 다른 문자를 조작 합니다.  이러한 문자 형식 형식인  **TCHAR**, `char`, 및 `wchar_t`, 각각.  이러한 기본 문자열 형식에서 atl에서 프로세스 힙이나 mfc에서의 CRT 힙 메모리를 할당 하는 문자열 관리자를 사용 합니다.  일반적인 응용 프로그램의 경우이 메모리 할당 스키마 충분합니다.  그러나 문자열 또는 다중 스레드 코드의 기본 메모리 관리자가 최적으로 수행 되지 않을 집중적으로 사용 하는 코드를 사용 합니다.  이 여기서는 메모리 관리의 기본 동작을 재정의 하는 방법을 설명 합니다. `CStringT`, 특히 할당자를 만드는 준비 작업을 최적화 합니다.  
  
-   [사용자 지정 문자열 관리자 구현 \(기본 방법\)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)  
  
-   [힙 경합 방지](../atl-mfc-shared/avoidance-of-heap-contention.md)  
  
-   [사용자 지정 문자열 관리자 구현 \(고급 방법\)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)  
  
-   [CFixedStringT: 예의 사용자 지정 문자열 관리자](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)  
  
## 참고 항목  
 [CustomString 샘플](../top/visual-cpp-samples.md)