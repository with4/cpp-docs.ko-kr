---
title: "Naked 함수 호출 | Microsoft Docs"
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
  - "에필로그 코드"
  - "naked 함수"
  - "naked 키워드[C++]"
  - "naked 키워드[C++], 저장소 클래스 특성"
  - "프롤로그 코드"
  - "가상 장치 드라이버"
  - "가상 장치 드라이버, naked 함수 호출"
  - "VXD 가상 장치 드라이버"
ms.assetid: 2a66847a-a43f-4541-a7be-c9f5f29b5fdb
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Naked 함수 호출
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 `naked` 특성으로 선언된 함수를 내보내면 프롤로그\/에필로그 코드가 없으므로 [인라인 어셈블러](../assembler/inline/inline-assembler.md)를 사용하여 사용자 지정 프롤로그\/에필로그 코드를 작성할 수 있습니다.  Naked 함수는 고급 기능으로 제공됩니다.  이 함수를 통해 C\/C\+\+ 이외의 컨텍스트에서 호출되는 함수를 선언할 수 있으므로 매개 변수의 위치와 유지되고 있는 레지스터에 대한 다양한 가정을 만들 수 있습니다.  예시에는 인터럽트 처리기와 같은 루틴이 포함됩니다.  이러한 기능은 VxD\(가상 장치 드라이버\) 작성에 특히 유용합니다.  
  
## 추가 정보  
  
-   [naked](../cpp/naked-cpp.md)  
  
-   [Naked 함수의 규칙 및 제한](../cpp/rules-and-limitations-for-naked-functions.md)  
  
-   [프롤로그\/에필로그 코드 작성 시 고려 사항](../cpp/considerations-for-writing-prolog-epilog-code.md)  
  
### Microsoft 전용 종료  
  
## 참고 항목  
 [호출 규칙](../cpp/calling-conventions.md)