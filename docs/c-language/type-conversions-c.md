---
title: "형식 변환 (C) | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "변환, 형식"
  - "형식 변환"
  - "정수 계열 확장"
  - "형식 캐스팅, 수행 시"
  - "형식 변환"
ms.assetid: d130ee7c-03c3-48f4-af7b-1fdba0d3b086
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 형식 변환 (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식 변환은 지정된 연산자와 피연산자 및 연산자의 형식에 따라 달라집니다.  다음과 같은 경우에 형식 변환이 수행됩니다.  
  
-   한 형식의 값이 다른 형식의 변수에 할당되거나, 연산자가 연산을 수행하기 전에 피연산자의 형식을 변환하는 경우  
  
-   한 형식의 값이 다른 형식으로 명시적으로 캐스팅되는 경우  
  
-   값이 인수로 함수에 전달되거나, 형식이 함수에서 반환되는 경우  
  
 문자, short 정수, 부호가 있거나 없는 모든 정수 비트 필드 또는 열거형 형식의 개체는 정수를 사용할 수 있는 모든 식에서 사용될 수 있습니다.  `int`가 원래 형식의 모든 값을 나타낼 수 있으면 해당 값이 `int`로 변환되고, 그렇지 않으면 `unsigned int`로 변환됩니다.  이 프로세스를 "정수 계열 확장"이라고 합니다. 정수 계열 확장은 값을 유지합니다.  즉, 확장 후의 값과 확장 전의 값이 동일한 것으로 보장됩니다.  자세한 내용은 [일반적인 산술 변환](../c-language/usual-arithmetic-conversions.md)을 참조하십시오.  
  
## 참고 항목  
 [식 및 인수](../c-language/expressions-and-assignments.md)