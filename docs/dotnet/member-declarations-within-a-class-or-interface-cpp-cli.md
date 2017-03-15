---
title: "클래스 또는 인터페이스 내에서 멤버 선언(C++/CLI) | Microsoft Docs"
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
helpviewer_keywords: 
  - "클래스 멤버, 선언 구문"
  - "멤버, 선언 구문"
ms.assetid: 95d312a4-198b-46f0-b8f5-15253807c55e
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 클래스 또는 인터페이스 내에서 멤버 선언(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 속성 및 연산자의 선언 방식이 Managed Extensions for C\+\+와 상당히 다르게 변경되었으며 Managed Extensions 디자인에서 노출되던 기본 구현 세부 사항이 이제는 숨겨집니다.  이벤트 선언도 또한 수정되었습니다.  
  
 Managed Extensions가 지원하지 않는 변경 사항의 범주 중 주요한 내용으로는 Managed Extensions에서 인라인으로 정의해야 했던 정적 생성자를 이제 아웃오브 라인으로 정의할 수 있다는 점과 대리 생성자라는 개념이 새로 도입되었다는 점을 들 수 있습니다.  
  
## 단원 내용  
 [속성 선언](../dotnet/property-declaration.md)  
 속성 선언의 변경 사항에 대해 설명합니다.  
  
 [속성 인덱스 선언](../dotnet/property-index-declaration.md)  
 인덱싱된 속성 선언의 변경 사항에 대해 설명합니다.  
  
 [대리자 및 이벤트](../dotnet/delegates-and-events.md)  
 대리자와 이벤트를 선언하는 구문의 변경 사항에 대해 설명합니다.  
  
 [가상 함수 봉인](../dotnet/sealing-a-virtual-function.md)  
 함수를 봉인하는 구문의 변경 사항에 대해 설명합니다.  
  
 [오버로드된 연산자](../dotnet/overloaded-operators.md)  
 연산자 오버로드의 변경 사항에 대해 설명합니다.  
  
 [변환 연산자의 변경 내용](../dotnet/changes-to-conversion-operators.md)  
 변환 연산자의 변경 사항에 대해 설명합니다.  
  
 [인터페이스 멤버 명시적 재정의](../dotnet/explicit-override-of-an-interface-member.md)  
 인터페이스 멤버를 명시적으로 재정의하는 메서드의 변경 사항에 대해 설명합니다.  
  
 [전용 가상 함수](../dotnet/private-virtual-functions.md)  
 파생 클래스에서 전용 가상 함수가 처리되는 방식의 변경 사항에 대해 설명합니다.  
  
 [Static Const Int 링크가 더 이상 리터럴이 아닙니다.](../dotnet/static-const-int-linkage-is-no-longer-literal.md)  
 `static const` 정수 계열 멤버가 링크되는 방식의 변경 사항 및 새로운 `literal` 키워드를 사용하여 상수를 명시적으로 선언하는 방법에 대해 설명합니다.  
  
## 참고 항목  
 [C\+\+\/CLI 마이그레이션 입문](../dotnet/cpp-cli-migration-primer.md)