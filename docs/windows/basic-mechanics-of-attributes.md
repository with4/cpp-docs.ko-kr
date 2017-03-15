---
title: "Basic Mechanics of Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributes [C++], inserting in code"
  - "attributes [C++], about attributes"
ms.assetid: dc2069c3-b9f3-4a72-965c-4e5208ce8e34
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Basic Mechanics of Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로젝트에 특성을 삽입 하는 방법은 다음 세 가지가 있습니다.  첫째, 수동으로 소스 코드에 삽입 하.  둘째, 프로젝트에서 개체의 속성 표를 사용 하 여 삽입할 수 있습니다.  마지막으로, 다양 한 마법사를 사용 하 여 삽입할 수 있습니다.  다양 한 마법사 및 속성 창을 사용 하 여에 대 한 자세한 내용은  [만들기 및 Visual C\+\+ 프로젝트 관리](../ide/creating-and-managing-visual-cpp-projects.md).  
  
 Visual C\+\+를 시작 합니다.NET에서 컴파일러 소스 파일에 특성의 존재를 인식 하 고 동적으로 구문 분석 하 고 컴파일하는 동안 확인 됩니다.  
  
 프로젝트를 빌드할 때로 이전에 컴파일러 개체 파일을 만드는 각 C\+\+ 소스 파일을 분석 합니다.  그러나 컴파일러 특성이 발견 되 면 해당 구문 분석 이며 구문적으로 확인 합니다.  컴파일러가 특성 공급자 코드 삽입 또는 컴파일 타임에 수정 하 고 동적으로 호출 합니다.  공급자의 구현 특성의 종류에 따라 다릅니다.  예를 들어, ATL 관련 특성을 atlprov.dll에서 구현 됩니다.  
  
 다음 그림은 컴파일러와 특성 공급자 간의 관계를 보여 줍니다.  
  
 ![구성 요소 특성 통신](../windows/media/vccompattrcomm.png "vcCompAttrComm")  
  
> [!NOTE]
>  특성 사용 소스 파일의 내용을 변경 하지 않습니다.  디버깅 세션 동안에 특성이 생성 된 코드를 볼 수 있습니다.  또한, 프로젝트에서 각 소스 파일에 대 한 대체 특성의 결과 표시 하는 텍스트 파일을 생성할 수 있습니다.  이 절차에 대 한 자세한 내용은  [\/Fx \(삽입 된 코드 병합\)](../build/reference/fx-merge-injected-code.md) 및  [삽입 한 코드 디버깅](../Topic/How%20to:%20Debug%20Injected%20Code.md).  
  
 대부분의 C\+\+ 구문과 마찬가지로 특성을 자신의 적절 한 사용법을 정의 하는 특성 집합을 가집니다.  이 특성의 컨텍스트 이름으로 참조 하 고 각 특성 참조 항목에 대 한 컨텍스트 특성 테이블에서 해결 됩니다.  예를 들어,는  [coclass](../windows/coclass.md) 특성 에서만 적용할 수 있습니다 기존 클래스 또는 구조체에 달리는  [cpp\_quote](../windows/cpp-quote.md) 특성은 C\+\+ 소스 파일 내에서 아무 곳 이나 삽입할 수 있습니다.  
  
## 참고 항목  
 [Concepts](../windows/attributed-programming-concepts.md)