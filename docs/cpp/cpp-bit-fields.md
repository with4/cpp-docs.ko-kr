---
title: "C++ 비트 필드 | Microsoft Docs"
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
  - "비트 필드"
  - "비트 필드"
  - "필드[C++], 비트"
ms.assetid: 6f4b62e3-cc1d-4e5d-bf34-05904104f71a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ 비트 필드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

클래스와 구조체는 정수 형식보다 작은 저장 공간을 차지하는 멤버를 포함할 수 있습니다.  이러한 멤버는 비트 필드로 지정됩니다.  비트 필드 *멤버\-선언자* 사양의 구문은 다음을 따릅니다.  
  
## 구문  
  
```  
  
declarator  : constant-expression  
```  
  
## 설명  
 선택 사항인 `declarator`는 프로그램에서 멤버에 액세스하는 데 사용하는 이름입니다.  정수 형식\(열거형 형식 포함\)이어야 합니다.  *constant\-expression*은 구조에서 멤버가 차지하는 비트 수를 지정합니다.  익명 비트 필드, 식별자가 없는 비트 필드 멤버를 안쪽 여백에 사용할 수 있습니다.  
  
> [!NOTE]
>  너비가 0인 명명되지 않은 비트 필드는 다음 비트 필드를 다음 `type` 경계에 강제로 맞춥니다\(여기서 `type`은 멤버의 형식\).  
  
 다음 예제에서는 비트 필드가 포함된 구조체를 선언합니다.  
  
```  
// bit_fields1.cpp  
// compile with: /LD  
struct Date {  
   unsigned short nWeekDay  : 3;    // 0..7   (3 bits)  
   unsigned short nMonthDay : 6;    // 0..31  (6 bits)  
   unsigned short nMonth    : 5;    // 0..12  (5 bits)  
   unsigned short nYear     : 8;    // 0..100 (8 bits)  
};  
```  
  
 다음 그림에서는 `Date` 형식 개체의 개념적 메모리 레이아웃을 보여 줍니다.  
  
 ![날짜 개체의 메모리 레이아웃](../cpp/media/vc38uq1.png "vc38UQ1")  
날짜 개체의 메모리 레이아웃  
  
 `nYear`는 길이가 8비트이며 선언된 형식인 **부호 없는 short**의 단어 경계를 벗어납니다.  따라서 새 **부호 없는 short**의 시작 부분에서 시작됩니다.  모든 비트 필드가 기본 형식의 한 개체에 맞아야 할 필요는 없습니다. 선언에서 요청된 비트 수에 따라 새 저장소 단위가 할당됩니다.  
  
 **Microsoft 전용**  
  
 비트 필드로 선언되는 데이터의 순서는 위의 그림에 나온 것처럼 낮은 비트에서 높은 비트의 순서입니다.  
  
 **Microsoft 전용 종료**  
  
 다음 예제와 같이 구조체 선언에 길이가 0인 명명되지 않은 필드가 포함된 경우  
  
```  
// bit_fields2.cpp  
// compile with: /LD  
struct Date {  
   unsigned nWeekDay  : 3;    // 0..7   (3 bits)  
   unsigned nMonthDay : 6;    // 0..31  (6 bits)  
   unsigned           : 0;    // Force alignment to next boundary.  
   unsigned nMonth    : 5;    // 0..12  (5 bits)  
   unsigned nYear     : 8;    // 0..100 (8 bits)  
};  
```  
  
 메모리 레이아웃은 다음 그림과 같습니다.  
  
 ![길이가 0인 비트 필드가 있는 날짜 개체의 레이아웃](../cpp/media/vc38uq2.png "vc38UQ2")  
길이가 0인 비트 필드가 있는 날짜 개체의 레이아웃  
  
 비트 필드의 기본 형식은 [기본 형식](../cpp/fundamental-types-cpp.md)의 설명대로 정수 형식이어야 합니다.  
  
## 비트 필드에 대한 제한  
 비트 필드에 대한 잘못된 연산은 다음과 같습니다.  
  
1.  비트 필드의 주소 가져오기  
  
2.  비트 필드를 사용하여 참조 초기화  
  
## 참고 항목  
 [클래스 및 구조체](../cpp/classes-and-structs-cpp.md)