---
title: "멤버 액세스 | Microsoft Docs"
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
  - "멤버 액세스, 오버로드된 연산자"
  - "멤버 선택 연산자"
  - "연산자 오버로드, 멤버 액세스 연산자"
  - "포인터, 스마트"
  - "스마트 포인터"
  - "스마트 포인터, 정의"
ms.assetid: 8c7b2c43-eb92-4d42-9a8e-61aa37d71333
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 멤버 액세스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

멤버 액세스 연산자\(**–\>**\)를 오버로드하여 클래스 멤버 액세스를 제어할 수 있습니다.  이 연산자는 이 사용법에서 단항 연산자로 간주되며 오버로드된 연산자 함수가 클래스 멤버 함수여야 합니다.  따라서 이러한 함수의 선언은 다음과 같습니다.  
  
## 구문  
  
```  
  
class-type *operator–>()  
```  
  
## 설명  
 여기서 *class\-type*은 이 연산자가 속한 클래스의 이름입니다.  멤버 액세스 연산자 함수는 비정적 멤버 함수여야 합니다.  
  
 이 연산자는 역참조나 개수 사용법에 앞서 포인터의 유효성을 검사하는 "스마트 포인터"를 구현하는 데 사용되며 종종 포인터 역참조 연산자와 함께 사용됩니다.  
  
 **.** 멤버 클래스 연산자를 오버로드할 수 없습니다.  
  
## 참고 항목  
 [연산자 오버로드](../cpp/operator-overloading.md)